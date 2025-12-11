# Security and Privacy Guide

This guide provides comprehensive information about protecting sensitive legal information in the .cases repository.

---

## Overview

Legal cases often involve highly sensitive, confidential, and privileged information. This guide ensures you handle such information appropriately while using this repository.

---

## Core Security Principles

### 1. Classification of Information

Before adding any information to the repository, classify it:

| Level | Description | Handling |
|-------|-------------|----------|
| **PUBLIC** | Non-sensitive procedural information | ✅ Can be in public repository |
| **INTERNAL** | Anonymized case information | ⚠️ Private repository only |
| **CONFIDENTIAL** | Client information, case strategy | 🚫 Do NOT commit to repository |
| **PRIVILEGED** | Attorney-client communications | 🚫 NEVER commit to repository |

### 2. The Anonymization Rule

**Everything in this repository must be anonymized.**

Instead of real information, use:

| Real Information | Anonymized Version |
|-----------------|-------------------|
| John Smith | Party A / Plaintiff / Client 1 |
| 123-45-6789 (SSN) | [REDACTED] |
| john@example.com | [EMAIL REDACTED] |
| 123 Main Street | [ADDRESS REDACTED] |
| ABC Corporation | Company X |
| Specific dollar amount | [AMOUNT REDACTED] or approximate range |

### 3. Attorney-Client Privilege

**CRITICAL:** Attorney-client privileged communications must NEVER be committed to this repository, even in anonymized form, unless:

- The repository is private
- Access is strictly controlled
- The communication is necessary for case management
- Appropriate security measures are in place

---

## Legal Compliance Requirements

### European Union - GDPR

**Regulation (EU) 2016/679**

Key requirements when handling personal data:

#### Lawful Basis (Art. 6)
You must have a lawful basis for processing personal data:
- Legal obligation (Art. 6(1)(c)) - processing for legal proceedings
- Legitimate interests (Art. 6(1)(f)) - case management
- Consent (if applicable)

#### Data Subject Rights
Individuals have rights to:
- Access their data (Art. 15)
- Rectification (Art. 16)
- Erasure/"Right to be forgotten" (Art. 17)
- Data portability (Art. 20)

#### Data Protection Principles (Art. 5)
- **Lawfulness, fairness, transparency**
- **Purpose limitation** - use data only for legal proceedings
- **Data minimization** - collect only what's necessary
- **Accuracy** - keep data accurate and up to date
- **Storage limitation** - don't keep data longer than necessary
- **Integrity and confidentiality** - protect against unauthorized access

#### Special Categories (Art. 9)
Extra protection for:
- Health data
- Criminal convictions data
- Biometric data
- Racial or ethnic origin
- Political opinions
- Religious beliefs
- Trade union membership
- Sexual orientation

**These should NOT be in the repository unless absolutely necessary and with explicit safeguards.**

#### Data Breach Notification (Art. 33-34)
- Notify supervisory authority within 72 hours
- Notify affected individuals if high risk

#### Penalties
- Up to €20 million or 4% of global annual turnover

### United States - Privacy Laws

#### Federal Laws

**1. Privacy Act of 1974 (5 U.S.C. § 552a)**
- Government handling of personal information
- Access and correction rights

**2. ECPA (18 U.S.C. §§ 2510-2522)**
- Electronic communications privacy
- Stored communications protection

**3. HIPAA (45 CFR Parts 160, 164)**
If handling health information:
- Administrative safeguards
- Physical safeguards
- Technical safeguards
- Minimum necessary standard

#### State Laws

**California Consumer Privacy Act (CCPA)**
- Right to know about data collected
- Right to delete
- Right to opt-out of sale
- Non-discrimination

**Other State Laws:**
- Virginia Consumer Data Protection Act (VCDPA)
- Colorado Privacy Act (CPA)
- Connecticut Data Privacy Act (CTDPA)
- Each state may have specific requirements

### Sweden - Dataskyddslagen

**Dataskyddslagen (2018:218)**

Implements GDPR in Sweden with additional provisions:

#### Key Sections
- **3 kap.** - Processing for legal claims (exemptions)
- **5 kap.** - Processing of criminal conviction data

#### Datainspektionen (Swedish DPA)
- Supervisory authority
- Can impose fines and corrective measures
- Must notify of data breaches

#### Swedish Secrecy Rules
**Offentlighets- och sekretesslagen (2009:400)**
- Specific confidentiality rules for legal proceedings
- Different rules for different types of cases

---

## Technical Security Measures

### Repository Security

#### 1. Repository Visibility

**RECOMMENDED: Private Repository**

```bash
# Repository should be private for legal matters
# Settings → Danger Zone → Change visibility → Private
```

#### 2. Access Control

- Enable two-factor authentication (2FA) for all users
- Limit collaborators to essential personnel only
- Use least privilege principle
- Regular access audits

#### 3. Branch Protection

```bash
# Protect main branch
# Settings → Branches → Add rule
```

Require:
- Pull request reviews before merging
- Status checks to pass
- Conversation resolution before merging
- No force pushes
- No deletions

#### 4. Security Alerts

Enable in Settings → Security:
- Dependabot alerts
- Dependabot security updates
- Code scanning
- Secret scanning

### File Security

#### 1. .gitignore Configuration

The repository includes a `.gitignore` file that automatically excludes:

```
*.confidential
*.private
*_CONFIDENTIAL.*
*_PRIVATE.*
personal_data/
client_data/
*.ssn
*.passport
*.id_docs
```

**Always verify files before committing:**

```bash
git status          # Check what will be committed
git diff           # Review changes
git add -p         # Add changes interactively
```

#### 2. Pre-commit Checks

Before each commit, verify:

- [ ] No personal names (except anonymized)
- [ ] No addresses
- [ ] No phone numbers
- [ ] No email addresses (except anonymized)
- [ ] No SSNs or identification numbers
- [ ] No financial account numbers
- [ ] No passwords or credentials
- [ ] No privileged communications

#### 3. Sensitive Data Handling

**For truly sensitive documents:**

1. **NEVER commit to Git**
2. Store in encrypted local storage
3. Use encryption tools:
   - VeraCrypt (encrypted volumes)
   - GPG (file encryption)
   - BitLocker (Windows)
   - FileVault (macOS)
   - LUKS (Linux)

Example GPG encryption:
```bash
# Encrypt a file
gpg --symmetric --cipher-algo AES256 sensitive_document.pdf

# Decrypt
gpg sensitive_document.pdf.gpg
```

### Communication Security

#### 1. Secure Channels

Use encrypted communication for sensitive discussions:
- Encrypted email (PGP/GPG)
- Signal or other E2E encrypted messaging
- Secure video conferencing
- In-person meetings for highly sensitive matters

#### 2. Email Security

When discussing cases via email:
- Use encryption when possible
- Don't include sensitive details in subject lines
- Be careful with "Reply All"
- Verify recipient addresses
- Use secure email providers

---

## Data Retention and Disposal

### Retention Requirements

Different jurisdictions have different requirements:

#### Legal Requirements

| Jurisdiction | Typical Retention Period |
|--------------|-------------------------|
| EU/GDPR | 6-10 years (varies by member state) |
| US Federal | 7 years (varies by case type) |
| US State | Varies (check specific state) |
| Sweden | 7-10 years (varies by case type) |

#### Best Practices

- Keep closed case files for minimum 7 years
- Keep criminal case files for minimum 10 years
- Document destruction dates
- Follow specific court orders

### Secure Disposal

When deleting cases:

1. **From Repository:**
   ```bash
   # Remove file from Git history entirely
   git filter-branch --force --index-filter \
     "git rm --cached --ignore-unmatch cases/CASE-XXX.md" \
     --prune-empty --tag-name-filter cat -- --all
   
   # Force push (be careful!)
   git push origin --force --all
   ```

2. **From Local Storage:**
   - Use secure deletion tools
   - Overwrite data multiple times
   - Destroy physical media if necessary

3. **From Backups:**
   - Update backup retention policies
   - Securely delete from backup systems

---

## Incident Response Plan

### If Sensitive Data is Accidentally Committed

**IMMEDIATE ACTIONS:**

1. **DO NOT PANIC** - Act quickly but carefully

2. **Assess the Exposure:**
   - What data was exposed?
   - Who had access?
   - How long was it exposed?
   - Was it in a public repository?

3. **Remove the Data:**
   ```bash
   # If just committed (not pushed)
   git reset --soft HEAD~1
   
   # If pushed, remove from history
   git filter-branch --force --index-filter \
     "git rm --cached --ignore-unmatch path/to/sensitive/file.md" \
     --prune-empty --tag-name-filter cat -- --all
   
   git push origin --force --all
   git push origin --force --tags
   ```

4. **Notify Affected Parties:**
   - Inform clients if their data was exposed
   - Follow breach notification requirements
   - Document the incident

5. **Legal Notifications:**
   
   **GDPR (EU):**
   - Notify Data Protection Authority within 72 hours
   - Notify affected individuals if high risk
   
   **CCPA (California):**
   - Notify affected individuals without unreasonable delay
   
   **Swedish DPA (Datainspektionen):**
   - Notify within 72 hours via online form

6. **Review and Prevent:**
   - How did this happen?
   - Update procedures to prevent recurrence
   - Additional training if needed
   - Enhanced pre-commit checks

### Reporting Security Vulnerabilities

If you discover a security issue:

1. **DO NOT** create a public issue
2. Email repository owner privately
3. Include:
   - Description of vulnerability
   - Steps to reproduce
   - Potential impact
   - Suggested fix (if known)
4. Allow reasonable time for fix before disclosure

---

## Compliance Checklist

### Initial Setup
- [ ] Repository is private
- [ ] .gitignore properly configured
- [ ] Access limited to authorized users
- [ ] 2FA enabled for all users
- [ ] Branch protection enabled
- [ ] Security alerts enabled

### Before Each Commit
- [ ] All information anonymized
- [ ] No personal identifiable information
- [ ] No privileged communications
- [ ] No confidential client data
- [ ] Changes reviewed carefully
- [ ] Commit message is appropriate

### Regular Maintenance
- [ ] Weekly access audit
- [ ] Monthly security review
- [ ] Quarterly procedure update
- [ ] Annual compliance audit
- [ ] Regular backups to secure location
- [ ] Test restore procedures

### Case Closure
- [ ] Documents archived per policy
- [ ] Retention schedule documented
- [ ] Disposal date planned
- [ ] Backups updated
- [ ] Access revoked for non-essential users

---

## Training and Awareness

### Required Knowledge

All users of this repository should understand:

1. **Data Protection Laws**
   - GDPR basics
   - Local privacy laws
   - Breach notification requirements

2. **Attorney-Client Privilege**
   - What is protected
   - How to maintain privilege
   - Consequences of waiver

3. **Anonymization Techniques**
   - What to redact
   - How to redact
   - Verification methods

4. **Git Security**
   - What gets committed
   - How to review changes
   - How to remove sensitive data

### Regular Training

- Security awareness training: Annually
- GDPR/privacy law updates: As regulations change
- Incident response drills: Annually
- Tool training: As needed

---

## Additional Resources

### Tools

**Encryption:**
- GPG: https://gnupg.org/
- VeraCrypt: https://www.veracrypt.fr/
- Cryptomator: https://cryptomator.org/

**Git Security:**
- git-secrets: https://github.com/awslabs/git-secrets
- gitleaks: https://github.com/gitleaks/gitleaks

**Password Management:**
- 1Password: https://1password.com/
- Bitwarden: https://bitwarden.com/
- KeePassXC: https://keepassxc.org/

### References

**GDPR:**
- Official Text: https://gdpr-info.eu/
- Guidelines: https://edpb.europa.eu/

**US Privacy:**
- NIST Cybersecurity Framework: https://www.nist.gov/cyberframework
- FTC Privacy Guidelines: https://www.ftc.gov/

**Swedish:**
- Datainspektionen: https://www.imy.se/
- Offentlighets- och sekretesslagen: https://www.riksdagen.se/

---

## Contact

For security concerns:
- **DO NOT** use public channels
- Contact repository administrator privately
- Use encrypted communication

---

**Remember:** When in doubt about whether information is safe to commit, DON'T commit it. It's always better to be overly cautious with legal and personal information.

---

**Last Updated:** 2025-12-11  
**Version:** 1.0
