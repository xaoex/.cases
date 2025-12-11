# Getting Started Guide

This guide will help you set up and start using the .cases repository for managing your legal cases.

---

## Prerequisites

Before you begin, you should have:

- ✅ A GitHub account
- ✅ Basic understanding of Git and GitHub
- ✅ A text editor (VS Code, Sublime Text, etc.)
- ✅ Basic understanding of Markdown formatting
- ✅ Awareness of data protection requirements (GDPR, privacy laws)

---

## Step 1: Set Up Your Repository

### Option A: Fork This Repository (Recommended for Personal Use)

1. Click the "Fork" button at the top of this repository
2. Choose your account as the destination
3. Clone your forked repository to your local machine:
   ```bash
   git clone https://github.com/YOUR-USERNAME/.cases.git
   cd .cases
   ```

### Option B: Use as Template

1. Click "Use this template" button
2. Create a new repository
3. Clone to your local machine

### Option C: Clone Directly

```bash
git clone https://github.com/xaoex/.cases.git
cd .cases
```

---

## Step 2: Configure Security Settings

### Make Repository Private (Highly Recommended)

1. Go to repository Settings
2. Scroll to "Danger Zone"
3. Click "Change visibility"
4. Select "Private"
5. Confirm the change

### Enable Security Features

1. Go to Settings → Security
2. Enable:
   - Dependency alerts
   - Security updates
   - Code scanning (if available)

### Set Up Branch Protection

1. Go to Settings → Branches
2. Add rule for `main` branch:
   - Require pull request reviews
   - Require status checks
   - Include administrators

---

## Step 3: Review the Security Policy

📖 **Read the [SECURITY.md](../../SECURITY.md) file carefully**

Key points:
- Never commit actual personal data
- Use anonymization for all parties
- Store sensitive documents offline
- Follow data protection regulations

---

## Step 4: Understand the File Structure

```
.cases/
├── cases/                      # Your case files go here
├── templates/                  # Templates for documents
│   └── CASE_TEMPLATE.md       # Main case template
├── docs/                       # Documentation
│   ├── wiki/                  # Wiki pages
│   └── LEGAL_REFERENCES.md    # Legal reference guide
├── .github/
│   └── ISSUE_TEMPLATE/        # Issue templates
├── CASE_REGISTRY.md           # Master case list
├── SECURITY.md                # Security policy
├── .gitignore                 # Files to exclude from Git
└── README.md                  # Repository overview
```

---

## Step 5: Create Your First Case

### 5.1 Copy the Template

```bash
cp templates/CASE_TEMPLATE.md cases/CASE-001_my-first-case.md
```

### 5.2 Open in Your Editor

```bash
# Using VS Code
code cases/CASE-001_my-first-case.md

# Or any other editor
nano cases/CASE-001_my-first-case.md
```

### 5.3 Fill in Case Information

Replace all bracketed placeholders `[like this]` with your information:

- **Case Reference Number:** Use sequential numbering (CASE-001, CASE-002, etc.)
- **Parties:** Use anonymized references (Party A, Party B, Client 1, etc.)
- **Dates:** Use YYYY-MM-DD format
- **Legal Basis:** Add relevant laws and citations
- **Facts:** Document chronologically with evidence references

**⚠️ IMPORTANT:** Do NOT include:
- Real names of parties
- Social security numbers
- Addresses
- Phone numbers
- Email addresses
- Other personal identifiable information

### 5.4 Save the File

Save your changes regularly as you work.

---

## Step 6: Create a GitHub Issue

GitHub Issues help track and manage your cases.

1. Go to the "Issues" tab
2. Click "New Issue"
3. Choose "New Legal Case" template
4. Fill in the information (use anonymized data)
5. Click "Submit new issue"

---

## Step 7: Update the Case Registry

Open `CASE_REGISTRY.md` and add your case to the appropriate section:

```markdown
| CASE-001 | Case Title - Anonymized | District Court | Civil | 2025-12-11 | Active | 2025-12-11 |
```

---

## Step 8: Commit Your Changes

```bash
# Check what files have changed
git status

# Add your new case file
git add cases/CASE-001_my-first-case.md

# Add the updated registry
git add CASE_REGISTRY.md

# Commit with a clear message
git commit -m "Add CASE-001: Initial case documentation"

# Push to GitHub
git push origin main
```

---

## Step 9: Set Up Reminders and Workflows

### Calendar Integration

1. Create calendar events for all deadlines
2. Set multiple reminders (1 week, 3 days, 1 day before)
3. Share calendar with relevant parties

### GitHub Features

- **Milestones:** Create milestones for major case events
- **Projects:** Use project boards for workflow tracking
- **Labels:** Tag issues with appropriate labels

---

## Step 10: Regular Maintenance

### Daily Tasks
- [ ] Check for approaching deadlines
- [ ] Review new communications
- [ ] Update case status if needed

### Weekly Tasks
- [ ] Review all active cases
- [ ] Update case registry
- [ ] Check for missed deadlines
- [ ] Backup repository

### Monthly Tasks
- [ ] Audit all cases for accuracy
- [ ] Review security compliance
- [ ] Archive closed cases
- [ ] Update procedures if needed

---

## Common Tasks

### Adding a New Case

1. Create case file from template
2. Create GitHub issue
3. Update case registry
4. Commit and push changes

### Updating a Case

1. Open the case file
2. Make your changes
3. Update "Last Updated" metadata
4. Create "Case Update" GitHub issue (optional)
5. Commit with descriptive message

### Closing a Case

1. Update case status to "Closed"
2. Add final outcome/resolution
3. Move to "Closed Cases" section in registry
4. Close associated GitHub issue
5. Archive documents per retention policy

### Research Legal Issues

1. Create "Legal Research Request" issue
2. Consult [LEGAL_REFERENCES.md](../LEGAL_REFERENCES.md)
3. Document findings in case file
4. Update issue with results

---

## Tips for Success

### Documentation Best Practices

✅ **DO:**
- Document everything immediately
- Use consistent formatting
- Keep chronological order
- Cross-reference related information
- Update regularly
- Use clear, concise language

❌ **DON'T:**
- Procrastinate documentation
- Use inconsistent naming
- Skip details "you'll remember"
- Commit sensitive data
- Forget to backup

### Organization Tips

1. **Use descriptive file names:** `CASE-001_contract-dispute.md`
2. **Tag appropriately:** Use GitHub labels effectively
3. **Link related items:** Reference related cases and issues
4. **Maintain the registry:** Keep CASE_REGISTRY.md current
5. **Archive regularly:** Move old cases to archive folder

### Security Reminders

🔒 **Always:**
- Anonymize all parties
- Review before committing
- Use private repository for sensitive matters
- Encrypt offline backup
- Follow data protection laws

---

## Getting Help

### Documentation Resources

- [Case Management Guide](Case-Management-Guide.md)
- [Legal References](Legal-References.md)
- [Security and Privacy](Security-and-Privacy.md)
- [FAQ](FAQ.md)

### Troubleshooting

**Problem:** Git conflicts when pushing
- **Solution:** Pull latest changes first: `git pull origin main`

**Problem:** Can't find template
- **Solution:** Check `templates/` directory exists and contains files

**Problem:** Unsure about legal citations
- **Solution:** Consult [LEGAL_REFERENCES.md](../LEGAL_REFERENCES.md)

---

## Next Steps

Now that you've set up your repository:

1. ✅ Review the [Case Management Guide](Case-Management-Guide.md)
2. ✅ Familiarize yourself with [Legal References](Legal-References.md)
3. ✅ Read [Security and Privacy](Security-and-Privacy.md) guidelines
4. ✅ Start documenting your cases
5. ✅ Establish your routine for updates

---

## Checklist: Getting Started

- [ ] Repository cloned/forked
- [ ] Repository made private
- [ ] Security policy reviewed
- [ ] File structure understood
- [ ] First case created from template
- [ ] GitHub issue created
- [ ] Case registry updated
- [ ] Changes committed and pushed
- [ ] Calendar reminders set
- [ ] Backup plan established

---

**Welcome to organized legal case management!**

For questions or issues, create a GitHub issue or consult the [FAQ](FAQ.md).

---

**Last Updated:** 2025-12-11  
**Version:** 1.0
