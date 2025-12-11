# Security Policy

## Handling Sensitive Legal Information

This repository is designed to manage legal case documentation. **EXTREME CAUTION** must be exercised to protect sensitive information.

## Security Guidelines

### 1. Personal Identifiable Information (PII)
- **NEVER** commit actual personal data (names, SSNs, addresses, etc.)
- Use placeholder values or anonymized data
- Review all commits before pushing

### 2. Confidential Legal Documents
- Mark sensitive documents with `_CONFIDENTIAL` or `_PRIVATE` suffixes
- These files are automatically excluded via `.gitignore`
- Store sensitive documents in secure, encrypted local storage

### 3. Client Information
- Do not include client names in public documentation
- Use case reference numbers instead
- Keep client correspondence private

### 4. Data Classification

| Classification | Examples | Storage |
|---------------|----------|---------|
| PUBLIC | Case templates, procedures | GitHub (this repo) |
| INTERNAL | Anonymized case summaries | Local encrypted storage |
| CONFIDENTIAL | Client data, evidence | Offline secure storage |
| RESTRICTED | Court sealed documents | Legal-approved storage only |

## Reporting Security Issues

If you discover a security vulnerability:

1. **DO NOT** create a public GitHub issue
2. Contact the repository owner directly via private communication
3. Provide details about the vulnerability
4. Allow time for remediation before disclosure

## Compliance

This repository should comply with:

- **EU GDPR** (General Data Protection Regulation)
- **US Privacy Laws** (varies by state)
- **Swedish Data Protection Act** (Dataskyddslagen)
- Attorney-Client Privilege requirements
- Court confidentiality orders

## Best Practices

1. ✅ Use encryption for sensitive files
2. ✅ Regular security audits
3. ✅ Access control (private repository recommended)
4. ✅ Two-factor authentication for all contributors
5. ✅ Regular backups to secure locations
6. ✅ Document retention policies
7. ✅ Secure communication channels

## Incident Response

In case of data exposure:

1. Immediately notify all affected parties
2. Remove sensitive data from repository history
3. Rotate any exposed credentials
4. Document the incident
5. Review and update security measures
6. Comply with breach notification laws (72 hours under GDPR)

## Contact

For security concerns, contact the repository maintainer through secure channels.

---

**Last Updated:** 2025-12-11
