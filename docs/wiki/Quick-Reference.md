# Quick Reference Guide

A one-page reference for common tasks and information.

---

## 🚀 Quick Start

```bash
# Create new case
cp templates/CASE_TEMPLATE.md cases/CASE-XXX_description.md

# Update registry
nano CASE_REGISTRY.md

# Commit changes
git add cases/CASE-XXX_description.md CASE_REGISTRY.md
git commit -m "Add CASE-XXX: Description"
git push origin main
```

---

## 📁 File Structure

```
.cases/
├── cases/                  # Case files
├── templates/              # Templates
├── docs/                   # Documentation
│   ├── wiki/              # Wiki pages
│   └── LEGAL_REFERENCES.md
├── .github/ISSUE_TEMPLATE/ # Issue templates
├── CASE_REGISTRY.md       # Master case list
└── SECURITY.md            # Security policy
```

---

## 📝 Naming Conventions

| Type | Format | Example |
|------|--------|---------|
| Case files | `CASE-XXX_description.md` | `CASE-001_contract-dispute.md` |
| Evidence | `DOC-XXX` | `DOC-001` |
| Witnesses | `WIT-XXX` | `WIT-001` |
| Dates | `YYYY-MM-DD` | `2025-12-11` |

---

## 🔐 Security Rules

### ✅ ALWAYS
- Anonymize all parties (Party A, Party B, etc.)
- Review before committing
- Use private repository for real cases
- Store sensitive docs offline in encrypted storage

### ❌ NEVER
- Commit real names or personal data
- Include SSNs, addresses, phone numbers
- Share privileged communications
- Ignore .gitignore warnings

---

## ⚖️ Legal Citation Formats

### EU
```
Regulation (EU) 2016/679 [GDPR]
Article 17 GDPR
Directive 2011/83/EU
```

### US
```
18 U.S.C. § 1030
U.S. Const. amend. IV
Miranda v. Arizona, 384 U.S. 436 (1966)
```

### Sweden
```
Brottsbalken (1962:700)
4 kap. 5 § BrB
Dataskyddslagen (2018:218)
```

---

## 📊 Case Statuses

| Status | Description |
|--------|-------------|
| Draft | Being prepared |
| Filed | Submitted to court |
| Active | In active litigation |
| Discovery | Evidence exchange phase |
| Pre-Trial | Preparing for trial |
| Trial | Currently in trial |
| Pending Decision | Awaiting ruling |
| Appealed | Under appeal |
| Settled | Resolved by settlement |
| Closed | Concluded |

---

## 🎯 Common Git Commands

```bash
# Check status
git status

# Add files
git add filename.md
git add .

# Commit
git commit -m "Description"

# Push
git push origin main

# Pull latest
git pull origin main

# View changes
git diff filename.md
```

---

## 📅 Deadline Management

1. **Receive deadline** → Log immediately
2. **Add to case file** → "Key Deadlines" section
3. **Create issue** → Use "Deadline Reminder" template
4. **Calendar entry** → With multiple reminders
5. **Work backwards** → Schedule preparation time

**Reminder Schedule:**
- Start work: Deadline minus [time needed]
- 1 week before
- 3 days before
- 1 day before
- 2 hours before

---

## 📋 Issue Templates

| Template | Use For |
|----------|---------|
| New Legal Case | Starting a new case |
| Case Update | Status changes |
| Deadline Reminder | Tracking deadlines |
| Legal Research | Research requests |
| Motion/Filing | Court filings |
| Appeal Case | Appeals |

---

## 📚 Key Laws Reference

### EU - GDPR
- Art. 15: Right to access
- Art. 17: Right to erasure
- Art. 77: Right to lodge complaint
- Art. 82: Right to compensation

### US - Privacy
- CFAA: 18 U.S.C. § 1030
- ECPA: 18 U.S.C. §§ 2510-2522
- 4th Amendment: Search and seizure

### Sweden - Criminal
- BrB 4:4 - Unlawful coercion
- BrB 4:5 - Unlawful threat
- BrB 5:1 - Defamation

---

## 🔧 Common Tasks

### Update Case
```bash
# Edit file
nano cases/CASE-XXX_description.md

# Commit
git add cases/CASE-XXX_description.md
git commit -m "Update CASE-XXX: [what changed]"
git push origin main
```

### Close Case
```bash
# Update status in file
# Move to archive
git mv cases/CASE-XXX.md cases/archive/2025/
git commit -m "Archive CASE-XXX (closed)"
git push origin main
```

### Create Backup
```bash
# Clone to backup location
git clone /path/to/.cases /backup/location/.cases

# Or add remote
git remote add backup https://backup-url.git
git push backup main
```

---

## 📞 Getting Help

| Question Type | Resource |
|--------------|----------|
| Setup | [Getting Started](Getting-Started.md) |
| Security | [Security & Privacy](Security-and-Privacy.md) |
| Workflows | [Case Management Guide](Case-Management-Guide.md) |
| Laws | [Legal References](../LEGAL_REFERENCES.md) |
| General | [FAQ](FAQ.md) |
| Issues | Create GitHub issue |

---

## ⚠️ Important Reminders

1. **This is NOT legal advice** - Consult an attorney
2. **Review security policy** - Read SECURITY.md
3. **Anonymize everything** - No real personal data
4. **Backup regularly** - Multiple secure locations
5. **Update promptly** - Document as events occur
6. **Check deadlines daily** - Never miss a deadline
7. **Commit often** - Small, frequent commits
8. **Use private repo** - For real legal matters

---

## 🔗 Quick Links

- [📋 Case Template](../../templates/CASE_TEMPLATE.md)
- [📊 Case Registry](../../CASE_REGISTRY.md)
- [⚖️ Legal References](../LEGAL_REFERENCES.md)
- [🔒 Security Policy](../../SECURITY.md)
- [📖 Wiki Home](Home.md)
- [🚀 Getting Started](Getting-Started.md)
- [❓ FAQ](FAQ.md)

---

## 💡 Pro Tips

1. **Work ahead** - Don't wait for deadlines
2. **Document everything** - Better to over-document
3. **Use issues** - Track tasks with GitHub issues
4. **Search first** - Check existing docs/issues
5. **Ask questions** - Create issue if unclear
6. **Stay organized** - Consistency is key
7. **Review security** - Weekly security check
8. **Test backups** - Verify you can restore

---

**Print this page for quick desk reference!**

---

**Last Updated:** 2025-12-11  
**Version:** 1.0
