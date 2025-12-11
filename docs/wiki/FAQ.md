# FAQ - Frequently Asked Questions

---

## General Questions

### Q: What is this repository for?

**A:** This repository provides a structured system for organizing and managing legal cases. It includes templates, tracking tools, and reference materials for EU, US, and Swedish legal matters.

---

### Q: Who can use this system?

**A:** This system can be used by:
- Legal professionals managing cases
- Individuals tracking their own legal matters
- Legal departments in organizations
- Law students for case study organization
- Anyone needing structured legal documentation

---

### Q: Do I need to be a lawyer to use this?

**A:** No, but you should:
- Consult with a qualified attorney for actual legal matters
- Understand that templates are for organization, not legal advice
- Follow all security and privacy guidelines
- Be aware of your jurisdiction's legal requirements

---

### Q: Is this system a replacement for legal advice?

**A:** **NO.** This is an organizational tool only. It does NOT:
- Provide legal advice
- Replace consultation with an attorney
- Create an attorney-client relationship
- Guarantee any legal outcome

Always consult a licensed attorney for legal advice.

---

## Security and Privacy

### Q: Is it safe to store case information here?

**A:** Only if you follow these rules:
- ✅ Use a **private repository** for sensitive matters
- ✅ **Anonymize all** personal information
- ✅ **Never commit** confidential documents or privileged communications
- ✅ Store sensitive documents in secure, encrypted offline storage
- ✅ Follow all security guidelines in [Security-and-Privacy.md](Security-and-Privacy.md)

---

### Q: How do I anonymize information?

**A:** Replace identifying information with generic references:

| Don't Use | Use Instead |
|-----------|-------------|
| Real names | Party A, Party B, Client 1, Defendant 2 |
| Real addresses | [ADDRESS REDACTED] or City, State only |
| Email addresses | [EMAIL REDACTED] |
| Phone numbers | [PHONE REDACTED] |
| SSN/Personal IDs | [ID REDACTED] |
| Company names | Company X, Organization Y |

---

### Q: What if I accidentally commit sensitive data?

**A:** Follow the incident response plan in [Security-and-Privacy.md](Security-and-Privacy.md):

1. Remove it immediately from Git history
2. Notify affected parties
3. Follow breach notification requirements (GDPR requires notification within 72 hours)
4. Document the incident
5. Update procedures to prevent recurrence

---

### Q: Should my repository be public or private?

**A:** For legal cases containing any real case information (even anonymized), use a **private repository**. Only use public repositories for:
- Generic templates (no real cases)
- Educational materials
- Completely fictional examples

---

### Q: What about attorney-client privilege?

**A:** Attorney-client privileged communications should generally NOT be committed to any repository. If absolutely necessary:
- Repository must be private
- Strict access controls
- Proper security measures
- Consult with your attorney first

---

## Using the System

### Q: How do I start my first case?

**A:** Follow these steps:

1. Copy the template:
   ```bash
   cp templates/CASE_TEMPLATE.md cases/CASE-001_description.md
   ```

2. Fill in the information (anonymized)

3. Create a GitHub issue using "New Legal Case" template

4. Update CASE_REGISTRY.md

5. Commit and push:
   ```bash
   git add cases/CASE-001_description.md CASE_REGISTRY.md
   git commit -m "Add CASE-001: Description"
   git push origin main
   ```

See [Getting Started Guide](Getting-Started.md) for detailed instructions.

---

### Q: How should I name my case files?

**A:** Use this format:
```
CASE-XXX_brief-description.md
```

Examples:
- `CASE-001_contract-dispute.md`
- `CASE-002_employment-matter.md`
- `CASE-003_appeal.md`

---

### Q: What if I have multiple related cases?

**A:** 
- Use separate files for each case
- Link them in the "Related Cases" section
- Use GitHub issues to cross-reference
- Create a label for the case group

Example:
```markdown
## Related Cases
- Primary case: CASE-001
- Related case: CASE-002 (same matter, different claim)
- Precedent: CASE-050
```

---

### Q: How do I track deadlines?

**A:** Use multiple methods:

1. **In the case file:** List in "Key Deadlines" section
2. **GitHub Issues:** Create "Deadline Reminder" issues
3. **GitHub Milestones:** Set milestone dates
4. **External calendar:** Add to your calendar with reminders
5. **CASE_REGISTRY.md:** Include in upcoming deadlines table

---

### Q: Can I use this for international cases?

**A:** Yes! The system includes references for:
- European Union law
- United States federal and state law
- Swedish law
- International treaties

For other jurisdictions, you can:
- Add relevant laws to LEGAL_REFERENCES.md
- Create custom sections in case template
- Document jurisdiction-specific procedures

---

## Technical Questions

### Q: What if I get Git conflicts?

**A:** 
```bash
# Pull the latest changes first
git pull origin main

# If conflicts occur, resolve them manually
# Edit conflicted files, keeping the correct version
# Look for markers: <<<<<<<, =======, >>>>>>>

# After resolving
git add resolved-file.md
git commit -m "Resolve merge conflict"
git push origin main
```

---

### Q: How do I backup my cases?

**A:** Use multiple backup methods:

1. **Git remotes:** Push to GitHub (and optionally other remotes)
2. **Local backups:** Regular copies to external drives
3. **Encrypted backups:** Use encrypted cloud storage
4. **Offline backups:** Physical media in secure location

```bash
# Add additional remote for backup
git remote add backup https://backup-location.git
git push backup main
```

---

### Q: Can multiple people work on the same case?

**A:** Yes, using Git collaboration:

1. Create branches for major changes:
   ```bash
   git checkout -b update-case-001
   # Make changes
   git commit -m "Update CASE-001 with new evidence"
   git push origin update-case-001
   ```

2. Create pull request for review

3. Merge after review

For sensitive cases:
- Limit access to authorized users only
- Use branch protection
- Require reviews before merging

---

### Q: How do I archive old cases?

**A:** 

1. Create archive directory:
   ```bash
   mkdir -p cases/archive/YYYY
   ```

2. Move closed cases:
   ```bash
   git mv cases/CASE-XXX.md cases/archive/YYYY/
   ```

3. Update CASE_REGISTRY.md to reflect archived status

4. Commit changes:
   ```bash
   git commit -m "Archive CASE-XXX"
   git push origin main
   ```

---

### Q: What format should I use for dates?

**A:** Always use ISO 8601 format: **YYYY-MM-DD**

Examples:
- December 11, 2025 → 2025-12-11
- January 5, 2024 → 2024-01-05

This ensures:
- Consistent formatting
- Proper sorting
- International compatibility

---

## Legal References

### Q: Where can I find legal citations?

**A:** Check [LEGAL_REFERENCES.md](../LEGAL_REFERENCES.md) for:
- Common EU regulations and directives
- US federal statutes
- Swedish laws
- Citation formats

For specific research, use:
- EUR-Lex (EU): https://eur-lex.europa.eu/
- Cornell LII (US): https://www.law.cornell.edu/
- Riksdagen (Sweden): https://www.riksdagen.se/

---

### Q: How do I cite laws properly?

**A:** Follow jurisdiction-specific formats:

**EU:**
```
Regulation (EU) 2016/679 [GDPR]
Directive 2011/83/EU
Article 17 GDPR
```

**US:**
```
18 U.S.C. § 1030 [CFAA]
U.S. Const. amend. IV
Miranda v. Arizona, 384 U.S. 436 (1966)
```

**Sweden:**
```
Brottsbalken (1962:700)
4 kap. 5 § BrB
Dataskyddslagen (2018:218)
```

See [LEGAL_REFERENCES.md](../LEGAL_REFERENCES.md) for more examples.

---

### Q: What if a law isn't in LEGAL_REFERENCES.md?

**A:** You can:
1. Add it yourself (submit a pull request)
2. Document it in your case file
3. Create an issue requesting it be added
4. Research it independently

Always verify current law with official sources.

---

## Case Management

### Q: How often should I update cases?

**A:** 

**Minimum:**
- Weekly status review
- Immediately when deadlines change
- After significant events (hearings, filings, etc.)

**Best Practice:**
- Daily check for active cases
- Document events same-day
- Update after every communication

---

### Q: What if case information changes?

**A:** 

1. Update the case file
2. Update "Last Updated" date in metadata
3. Add note in "Status Updates" section
4. Create "Case Update" GitHub issue if significant
5. Commit with descriptive message:
   ```bash
   git commit -m "Update CASE-001: Add new evidence DOC-015"
   ```

---

### Q: How do I handle appeals?

**A:** 

**Option 1: New Case File**
```
CASE-001_original-matter.md
CASE-002_appeal-of-case-001.md
```

**Option 2: Same File with Sections**
Add appeal sections to original case file

**Both:** 
- Update CASE_REGISTRY.md Appeals section
- Link original and appeal cases
- Track both in separate GitHub issues

---

### Q: What about settled cases?

**A:** 

1. Update case status to "Settled"
2. Document settlement terms (if not confidential)
3. Record outcome in "Requested Relief" section
4. Move to "Closed Cases" in registry
5. Close GitHub issue
6. Follow retention policy for archiving

⚠️ **Never include confidential settlement terms in the repository**

---

## Troubleshooting

### Q: Git says file is too large

**A:** GitHub has file size limits (100 MB max, 50 MB warning).

**Solution:**
- Don't commit large documents (use encrypted offline storage)
- Use Git LFS for large files if absolutely necessary
- Store large files outside repository

---

### Q: I can't find my case file

**A:** 

1. Check all case directories:
   ```bash
   find . -name "*CASE-001*"
   ```

2. Check Git history:
   ```bash
   git log --all --full-history -- cases/CASE-001*.md
   ```

3. Check if it was moved to archive

---

### Q: Changes aren't showing on GitHub

**A:** 

1. Verify changes are committed:
   ```bash
   git status
   ```

2. Push to remote:
   ```bash
   git push origin main
   ```

3. Check you're on correct branch:
   ```bash
   git branch
   ```

---

## Compliance

### Q: Does this comply with GDPR?

**A:** The system is **designed** to support GDPR compliance, but compliance depends on how you use it:

✅ **Compliant if you:**
- Anonymize all personal data
- Don't commit sensitive data
- Follow security guidelines
- Respect data subject rights
- Follow retention policies

❌ **Not compliant if you:**
- Commit actual personal data
- Use public repository for real cases
- Ignore security measures
- Violate data subject rights

See [Security-and-Privacy.md](Security-and-Privacy.md) for full GDPR guidance.

---

### Q: What about CCPA or other US privacy laws?

**A:** Similar principles apply:
- Minimize data collection
- Anonymize when possible
- Don't commit personal information
- Respect privacy rights
- Follow breach notification requirements

---

### Q: How long should I keep case files?

**A:** Retention periods vary by jurisdiction:

| Jurisdiction | Typical Period |
|--------------|---------------|
| EU/GDPR | 6-10 years |
| US Federal | 7 years |
| US State | Varies by state |
| Sweden | 7-10 years |

Check your specific jurisdiction and case type. Some cases (especially criminal) may require longer retention.

---

## Getting Help

### Q: Where can I get more help?

**A:** Resources:

1. **Documentation:**
   - [Getting Started Guide](Getting-Started.md)
   - [Case Management Guide](Case-Management-Guide.md)
   - [Security and Privacy](Security-and-Privacy.md)
   - [Wiki Home](Home.md)

2. **GitHub:**
   - Search existing issues
   - Create new issue
   - Check discussions

3. **Legal Advice:**
   - Consult qualified attorney
   - Contact local bar association
   - Legal aid organizations

---

### Q: Can I contribute to this project?

**A:** Yes! Contributions are welcome:

1. Fork the repository
2. Make improvements
3. Submit pull request
4. Follow contribution guidelines

Good contributions:
- Documentation improvements
- Additional legal references
- Template enhancements
- Bug fixes
- Translation to other languages

---

### Q: I found a bug or security issue, what should I do?

**A:** 

**For bugs:**
- Create a GitHub issue with details
- Include steps to reproduce
- Describe expected vs actual behavior

**For security issues:**
- **DO NOT** create public issue
- Contact repository owner privately
- Use encrypted communication
- Follow responsible disclosure

---

## Still Have Questions?

If your question isn't answered here:

1. Check other wiki pages
2. Search existing GitHub issues
3. Create a new issue with your question
4. Consult with legal counsel for legal questions

---

**Last Updated:** 2025-12-11  
**Version:** 1.0

---

**Remember:** This is an organizational tool, not legal advice. Always consult a qualified attorney for legal matters.
