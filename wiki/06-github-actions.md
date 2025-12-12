# GitHub Actions & Automation

## Overview

This repository uses GitHub Actions to automate security, quality control, notifications, and maintenance tasks. Automation reduces manual work, prevents errors, and ensures consistent processes.

## Automated Workflows

### Security & Privacy

#### Sensitive Data Detection Workflow
**File**: `.github/workflows/sensitive-data-scan.yml`  
**Trigger**: On all pull requests  
**Purpose**: Prevent accidental commit of PII

**Detects**:
- Social Security Numbers (SSN)
- Swedish Personnummer
- Credit card numbers
- Email addresses (in sensitive contexts)
- Phone numbers
- Bank account numbers
- API keys and tokens
- Passwords
- Medical record numbers
- Case numbers that may identify individuals

**Actions**:
- Scans all changed files
- Blocks merge if sensitive data detected
- Creates issue for review
- Notifies repository admins

**Bypass**: False positives can be approved by admin

#### Security Scanning Workflow
**File**: `.github/workflows/security-scan.yml`  
**Trigger**: Daily + on pull requests  
**Purpose**: Identify security vulnerabilities

**Tools**:
- CodeQL analysis
- Dependabot alerts
- Secret scanning
- Dependency vulnerability checks

**Actions**:
- Creates security advisories
- Auto-creates PRs for dependency updates
- Notifies security team
- Generates security reports

### Quality Control

#### Markdown Linting Workflow
**File**: `.github/workflows/markdown-lint.yml`  
**Trigger**: On pull requests  
**Purpose**: Ensure consistent markdown formatting

**Checks**:
- Consistent heading styles
- Proper list formatting
- No trailing spaces
- Consistent link styles
- Proper code block formatting
- Table formatting
- Line length limits (where appropriate)

**Configuration**: `.markdownlint.json`

#### Link Validation Workflow  
**File**: `.github/workflows/link-check.yml`  
**Trigger**: Weekly + on pull requests  
**Purpose**: Ensure all links work

**Validates**:
- Internal markdown links
- Relative file paths
- Anchor links within documents
- Links to issues and PRs
- External links (with rate limiting)

**Actions**:
- Creates issue for broken links
- Generates link report
- Suggests fixes

#### Spell Check Workflow
**File**: `.github/workflows/spell-check.yml`  
**Trigger**: On pull requests  
**Purpose**: Maintain professional quality

**Features**:
- Legal terminology dictionary
- Medical terminology dictionary
- Swedish language support
- Custom dictionary for case-specific terms
- Ignore proper names
- Ignore code blocks

**Tool**: cspell

### Case Management Automation

#### Deadline Reminder Workflow
**File**: `.github/workflows/deadline-reminder.yml`  
**Trigger**: Daily at 9 AM UTC  
**Purpose**: Never miss important deadlines

**Monitors**:
- Milestone due dates
- Project deadline fields
- Court filing dates
- Statute of limitations
- Discovery deadlines
- Appeal deadlines

**Notifications**:
- 1 week before: Issue comment + label
- 3 days before: Issue comment + email (if configured)
- 1 day before: Critical notification + email
- On deadline: Final notification
- Past deadline: Creates "overdue" issue

#### Evidence Backup Workflow
**File**: `.github/workflows/evidence-backup.yml`  
**Trigger**: Daily at 2 AM UTC  
**Purpose**: Protect critical evidence

**Process**:
1. Compress evidence directory
2. Encrypt with GPG
3. Upload to backup location(s)
4. Verify upload integrity
5. Log completion
6. Rotate old backups (retain 90 days)

**Storage**:
- Primary: Cloud storage
- Secondary: Geographic redundancy
- Tertiary: Local encrypted backup

#### Case Status Update Workflow
**File**: `.github/workflows/case-status-update.yml`  
**Trigger**: On issue close, label change  
**Purpose**: Auto-update case progress

**Logic**:
- All evidence issues closed → "Evidence Complete"
- All timeline issues closed → "Timeline Complete"
- All documentation issues closed → "Documentation Complete"
- All prerequisite issues closed → "Ready for Filing"

**Actions**:
- Updates project board status
- Updates milestone progress
- Sends notifications
- Generates progress report

### Reporting & Metrics

#### Weekly Summary Report Workflow
**File**: `.github/workflows/weekly-summary.yml`  
**Trigger**: Every Monday at 9 AM  
**Purpose**: Track progress and activity

**Report Includes**:
- Issues opened/closed this week
- PRs merged
- Evidence items added
- Timeline entries added
- Upcoming deadlines
- Task completion rate
- Blockers and delays
- Team velocity

**Distribution**:
- Posted as GitHub issue
- Email to stakeholders (if configured)
- Added to project board

#### Metrics Collection Workflow
**File**: `.github/workflows/metrics-collection.yml`  
**Trigger**: Daily  
**Purpose**: Track repository health

**Metrics**:
- Issue resolution time
- Evidence collection rate
- Documentation completion percentage
- Deadline adherence rate
- PR merge time
- Active contributors
- Code quality scores
- Security scan results

**Storage**: Metrics database or GitHub repository

### Maintenance Automation

#### Issue Triage Workflow
**File**: `.github/workflows/issue-triage.yml`  
**Trigger**: On new issue creation  
**Purpose**: Auto-categorize and assign

**Rules**:
- Contains "evidence" → Label: `evidence`
- Contains "deadline" → Label: `priority:high`
- Contains "security" → Label: `priority:critical`, notify security team
- Contains case number → Label: `case-001`
- Contains "wiki" → Label: `wiki`

#### Stale Issue Management Workflow
**File**: `.github/workflows/stale-issues.yml`  
**Trigger**: Daily  
**Purpose**: Manage inactive issues

**Rules**:
- No activity for 60 days → Label: `stale`
- Stale for 14 more days → Close with message
- Activity removes `stale` label
- Exempt labels: `priority:critical`, `evidence`, `legal`

#### Document Versioning Workflow
**File**: `.github/workflows/document-versioning.yml`  
**Trigger**: On changes to critical documents  
**Purpose**: Version control for legal documents

**Process**:
- Detects changes to docs/cases/ or docs/legal-filings/
- Creates version tag
- Archives previous version
- Generates changelog
- Creates GitHub release (for major versions)

**Versioning**: Semantic versioning (v1.0.0, v1.1.0, etc.)

#### PR Auto-Merge Workflow
**File**: `.github/workflows/auto-merge.yml`  
**Trigger**: On PR approval  
**Purpose**: Auto-merge safe updates

**Criteria**:
- Dependabot PRs (minor/patch versions only)
- All status checks passing
- At least 1 approval
- No merge conflicts
- Labeled: `dependencies`

**Safety**:
- Never auto-merge major version updates
- Never auto-merge anything labeled `manual-review`
- Always notify on merge

## Notification System

### Notification Channels

#### GitHub Notifications
- Issue comments
- PR reviews
- Mentions (@username)
- Assignee notifications
- Milestone notifications

#### Email Notifications (Optional)
- Critical deadlines
- Security alerts
- Weekly summaries
- Admin notifications

#### Slack/Discord Integration (Optional)
- Real-time updates
- Team mentions
- Custom channels per case
- Bot commands

### Notification Routing

**Priority Routing**:
- `priority:critical` → Email + GitHub + Slack (if configured)
- `priority:high` → GitHub + Slack (if configured)
- `priority:medium` → GitHub
- `priority:low` → GitHub (batched)

**Category Routing**:
- Evidence updates → Evidence manager
- Legal deadlines → Legal team + Email
- Security alerts → Security team immediately
- Documentation updates → Documentation channel
- Case updates → Case owner

## Workflow Permissions

All workflows use principle of least privilege:

```yaml
permissions:
  contents: read          # Read repository contents
  issues: write          # Create and update issues
  pull-requests: write   # Comment on PRs
  security-events: write # Submit security findings
```

Never use `write-all` or overly broad permissions.

## Secrets Management

### Required Secrets
- `GPG_PRIVATE_KEY` - For evidence encryption
- `BACKUP_TOKEN` - For backup storage access
- `SLACK_WEBHOOK` - For Slack notifications (optional)
- `EMAIL_API_KEY` - For email notifications (optional)

### Best Practices
- Rotate secrets quarterly
- Use GitHub Secrets (encrypted)
- Never commit secrets to repository
- Use environment-specific secrets
- Audit secret access regularly

## Custom Actions

### Evidence Validator
Custom action to validate evidence submissions:
- Checks chain of custody documentation
- Verifies file integrity
- Ensures metadata completeness
- Validates file formats

### Timeline Validator
Custom action to validate timeline entries:
- Checks chronological order
- Verifies date formats
- Ensures cross-references exist
- Validates completeness

### Legal Citation Checker
Custom action to validate legal citations:
- Checks citation format
- Validates case law references
- Ensures statute citations correct
- Checks jurisdiction appropriateness

## Workflow Triggers

### Event Triggers
- `push` - Code pushed to repository
- `pull_request` - PR opened/updated
- `issues` - Issue created/updated
- `release` - Release published
- `schedule` - Cron-based scheduling
- `workflow_dispatch` - Manual trigger

### Schedule Examples
```yaml
# Daily at 2 AM UTC
schedule:
  - cron: '0 2 * * *'

# Weekly on Monday at 9 AM UTC
schedule:
  - cron: '0 9 * * 1'

# Monthly on 1st at midnight UTC
schedule:
  - cron: '0 0 1 * *'
```

## Workflow Development

### Testing Workflows
1. Create in separate branch
2. Use `workflow_dispatch` for manual testing
3. Test with dummy data
4. Verify notifications work
5. Check permissions
6. Review logs
7. Merge when validated

### Debugging Workflows
- Check Actions tab for run logs
- Use `set -x` for bash debugging
- Add debug statements
- Check permissions
- Verify secrets are set
- Test locally when possible (act tool)

### Workflow Best Practices
- ✅ Use specific action versions (not `@main`)
- ✅ Minimize workflow runtime
- ✅ Use caching when appropriate
- ✅ Handle errors gracefully
- ✅ Provide clear failure messages
- ✅ Document workflow purpose
- ✅ Test thoroughly before deploying

## Monitoring & Maintenance

### Workflow Monitoring
- Check Actions tab daily
- Review failed workflows immediately
- Monitor workflow run times
- Check usage limits
- Review security alerts

### Maintenance Tasks
- Update action versions quarterly
- Review and optimize slow workflows
- Remove unused workflows
- Update documentation
- Rotate secrets
- Archive old workflow runs

## Cost Optimization

### GitHub Actions Minutes
- Public repositories: Unlimited (with fair use)
- Private repositories: Quota-based

**Optimization Tips**:
- Use caching to reduce build times
- Cancel redundant workflow runs
- Use `if` conditions to skip unnecessary steps
- Schedule heavy workflows during off-peak
- Use self-hosted runners for intensive tasks

## Security Considerations

### Workflow Security
- ✅ Never expose secrets in logs
- ✅ Validate all inputs
- ✅ Use verified actions only
- ✅ Pin action versions
- ✅ Limit workflow permissions
- ✅ Review workflow changes carefully
- ✅ Monitor for unusual activity

### Third-Party Actions
Only use actions from:
- GitHub official actions
- Verified creators
- Well-maintained repositories
- Actions with security audit

## Extending Automation

### Adding New Workflows
1. Identify manual process to automate
2. Define workflow requirements
3. Create workflow file
4. Test thoroughly
5. Document workflow
6. Train team on new automation
7. Monitor after deployment

### Custom Integrations
Workflows can integrate with:
- External case management systems
- Document storage services
- Communication platforms
- Calendar applications
- Time tracking tools
- Legal research databases

## Resources

### GitHub Actions Documentation
- [Workflow Syntax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)
- [Events that Trigger Workflows](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows)
- [Encrypted Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

### Workflow Examples
- [GitHub Actions Examples](https://github.com/actions/examples)
- [Awesome Actions](https://github.com/sdras/awesome-actions)

### Related Wiki Pages
- [Issue Management System](./05-issue-management.md)
- [Security & Privacy](./11-security.md)
- [Repository Structure](./20-case-organization.md)

---

**Last Updated:** 2024-12-12  
**Status**: Workflows specifications complete, implementation in progress
