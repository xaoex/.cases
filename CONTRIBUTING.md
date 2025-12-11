# Contributing to .cases

Thank you for your interest in contributing to the .cases legal case management system!

---

## Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inclusive environment for all contributors.

### Expected Behavior

- ✅ Be respectful and professional
- ✅ Use welcoming and inclusive language
- ✅ Accept constructive criticism gracefully
- ✅ Focus on what's best for the community
- ✅ Show empathy toward others

### Unacceptable Behavior

- ❌ Harassment or discriminatory language
- ❌ Personal attacks or insults
- ❌ Trolling or inflammatory comments
- ❌ Publishing others' private information
- ❌ Unethical or unprofessional conduct

---

## How to Contribute

### Types of Contributions

We welcome various types of contributions:

1. **Documentation Improvements**
   - Fixing typos or unclear explanations
   - Adding examples
   - Translating to other languages
   - Improving clarity

2. **Legal References**
   - Adding citations for additional jurisdictions
   - Updating legal references
   - Adding case law examples
   - Documenting procedural rules

3. **Template Enhancements**
   - Improving case template structure
   - Adding new template variations
   - Making templates more comprehensive

4. **Bug Fixes**
   - Fixing errors in documentation
   - Correcting broken links
   - Fixing formatting issues

5. **New Features**
   - Additional GitHub issue templates
   - Workflow automations
   - Integration tools
   - Organizational improvements

6. **Security Improvements**
   - Enhanced security guidelines
   - Better anonymization tools
   - Privacy enhancements

---

## Getting Started

### 1. Fork the Repository

Click the "Fork" button at the top right of the repository page.

### 2. Clone Your Fork

```bash
git clone https://github.com/YOUR-USERNAME/.cases.git
cd .cases
```

### 3. Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/your-bug-fix
```

Branch naming conventions:
- `feature/` - for new features
- `fix/` - for bug fixes
- `docs/` - for documentation changes
- `security/` - for security improvements

### 4. Make Your Changes

Edit the relevant files using your preferred editor.

### 5. Test Your Changes

- Review all changes carefully
- Check for typos and errors
- Verify markdown formatting
- Test any links
- Ensure security guidelines are followed

### 6. Commit Your Changes

```bash
git add .
git commit -m "Brief description of changes"
```

Commit message guidelines:
- Use present tense ("Add feature" not "Added feature")
- Be concise but descriptive
- Reference issues if applicable (#123)

### 7. Push to Your Fork

```bash
git push origin feature/your-feature-name
```

### 8. Create a Pull Request

1. Go to your fork on GitHub
2. Click "New Pull Request"
3. Select your branch
4. Fill in the PR template
5. Submit for review

---

## Pull Request Guidelines

### PR Title Format

```
[Type] Brief description

Examples:
[Docs] Update Getting Started guide
[Fix] Correct GDPR citation in legal references
[Feature] Add appeal case template
[Security] Enhance anonymization guidelines
```

### PR Description Should Include

1. **What:** What changes were made
2. **Why:** Why these changes are needed
3. **How:** How the changes were implemented
4. **Testing:** How changes were tested
5. **References:** Related issues or discussions

### PR Checklist

Before submitting, ensure:

- [ ] Changes are focused and related
- [ ] Documentation is updated
- [ ] No sensitive information included
- [ ] Markdown is properly formatted
- [ ] Links are tested and work
- [ ] Spelling and grammar checked
- [ ] Follows existing style and conventions
- [ ] Commit messages are clear

---

## Style Guidelines

### Markdown Formatting

```markdown
# Top-level heading (H1) - Used sparingly

## Main sections (H2)

### Subsections (H3)

#### Details (H4)

**Bold** for emphasis
*Italic* for terms
`Code` for commands and filenames
```

### File Naming

- Use kebab-case: `case-management-guide.md`
- Be descriptive but concise
- Use .md extension for markdown files

### Legal Citations

Follow jurisdiction-specific formats (see LEGAL_REFERENCES.md):

**EU:**
```markdown
Regulation (EU) 2016/679 [GDPR]
Article 17 GDPR
```

**US:**
```markdown
18 U.S.C. § 1030
U.S. Const. amend. IV
```

**Sweden:**
```markdown
Brottsbalken (1962:700)
4 kap. 5 § BrB
```

### Documentation Structure

Each documentation file should include:

1. Title (H1)
2. Brief introduction
3. Table of contents (for long docs)
4. Main content with clear sections
5. Related resources/links
6. Last updated date

---

## Types of Contributions in Detail

### Documentation

**What we need:**
- Clearer explanations
- More examples
- Better organization
- Typo fixes
- Updated information

**How to contribute:**
1. Identify areas that need improvement
2. Make changes in your fork
3. Submit PR with explanation

### Legal References

**What we need:**
- Additional jurisdiction references
- Updated statute citations
- Case law examples
- Procedural rules

**How to contribute:**
1. Research authoritative sources
2. Use proper citation format
3. Include brief explanation
4. Verify accuracy
5. Submit PR with sources

**Requirements:**
- Must cite official/authoritative sources
- Must be current law
- Must include proper citations
- Must specify jurisdiction

### Templates

**What we need:**
- Improved organization
- Additional sections
- Better instructions
- Specialized templates

**How to contribute:**
1. Identify template limitations
2. Propose improvements
3. Test with sample case
4. Submit PR with explanation

### Translations

**What we need:**
- Documentation in other languages
- Localized legal references
- Cultural considerations

**How to contribute:**
1. Create language directory: `docs/wiki/[lang]/`
2. Translate core documents
3. Adapt examples for local context
4. Submit PR

**Priority languages:**
- Swedish (svenska)
- German (Deutsch)
- French (Français)
- Spanish (Español)

---

## Security Considerations

### When Contributing

**Always:**
- ✅ Review changes for sensitive information
- ✅ Use anonymized examples
- ✅ Follow security guidelines
- ✅ Test security features

**Never:**
- ❌ Include real personal data
- ❌ Commit actual case information
- ❌ Include confidential information
- ❌ Weaken security measures

### Reporting Security Issues

If you find a security vulnerability:

1. **DO NOT** create a public issue
2. Email the repository owner privately
3. Describe the vulnerability
4. Suggest fix if possible
5. Allow time for remediation

---

## Review Process

### What to Expect

1. **Initial Review** (1-3 days)
   - Maintainer reviews PR
   - Provides feedback if needed

2. **Discussion** (as needed)
   - Address questions/concerns
   - Make requested changes

3. **Approval** (when ready)
   - PR is approved
   - Merged into main branch

4. **Acknowledgment**
   - Contributors credited
   - Changes go live

### Common Reasons for Changes Requested

- Unclear or missing documentation
- Incorrect legal citations
- Security concerns
- Formatting issues
- Incomplete implementation
- Out of scope

---

## Communication

### Where to Discuss

- **GitHub Issues:** Bug reports, feature requests
- **Pull Requests:** Specific code/doc changes
- **Discussions:** General questions, ideas

### Response Time

- We aim to respond to issues within 3 days
- PRs reviewed within 1 week
- Complex changes may take longer

---

## Recognition

Contributors will be recognized in:
- GitHub contributors list
- CONTRIBUTORS.md file (if created)
- Release notes (for significant contributions)

---

## Questions?

If you have questions about contributing:

1. Check this guide
2. Search existing issues
3. Create a new issue with "question" label
4. Be specific about what you need help with

---

## Legal Notice

By contributing, you agree that:

1. Your contributions are your original work
2. You have rights to submit the contribution
3. Your contribution is licensed under the repository's license
4. You understand this is not legal advice
5. You won't include confidential information

---

## Thank You!

Every contribution helps make this system better for everyone managing legal cases. We appreciate your time and effort!

---

**Last Updated:** 2025-12-11  
**Version:** 1.0
