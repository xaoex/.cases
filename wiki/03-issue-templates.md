# Issue Template Guide

## Overview

This repository provides four specialized issue templates for tracking different aspects of legal case documentation. This guide explains when and how to use each template effectively.

## Template Selection Guide

### Quick Reference

| Template | Use For | Create When |
|----------|---------|-------------|
| **Incident Report** | Harmful events or problems | Each time something harmful occurs |
| **Evidence Tracking** | Individual pieces of evidence | Each piece of evidence collected |
| **Damages Claim** | Financial or non-financial harm | Each category of damages |
| **Timeline Entry** | Significant chronological events | Each notable event or action |

## Incident Report Template

### When to Use

Create an Incident Report issue when:
- A harmful event occurs
- Someone does something wrong or harmful
- A problem arises that may be legally relevant
- A breach of contract or duty occurs
- You experience mistreatment or harm
- A violation happens

### What to Include

**Be Specific:**
- Exact dates and times (YYYY-MM-DD HH:MM timezone)
- Complete location information
- All people present or involved
- Exactly what was said or done
- Sequence of events

**Be Factual:**
- Describe what happened, not your interpretation
- Use direct quotes when possible
- Avoid subjective characterizations
- Distinguish between what you saw/heard and what you were told

**Be Complete:**
- Include all relevant details
- Note who witnessed events
- Describe immediate impact
- Document any evidence collected
- Link to related incidents

### Example Scenarios

**Employment:**
- Wrongful termination
- Harassment or discrimination
- Wage theft or unpaid wages
- Breach of employment contract
- Hostile work environment events

**Contract:**
- Breach of contract
- Non-payment
- Failure to perform
- Fraudulent misrepresentation
- Contract violations

**Personal:**
- Injury-causing events
- Property damage
- Defamation
- Privacy violations
- Assault or threats

**Consumer:**
- Defective products
- Fraudulent sales practices
- Service failures
- Warranty breaches
- Deceptive advertising

### Template Sections Explained

**Incident Information:**
- **ID:** Create unique identifier (e.g., INC-001, INC-002)
- **Date/Time:** Be as precise as possible
- **Location:** Specific address or location

**Description:**
- **What Happened:** Chronological, factual narrative
- **Parties Involved:** Everyone present with roles
- **Witnesses:** Anyone who saw/heard events

**Impact Assessment:**
- **Immediate:** What happened right away
- **Long-term:** Ongoing effects
- **Financial:** Dollar amounts if known
- **Personal:** Emotional, physical, or reputational harm

**Evidence:**
- Check all applicable boxes
- List specific items
- Note where evidence is stored

**Legal Relevance:**
- Laws you believe were violated
- Contractual obligations breached
- Rights infringed upon

## Evidence Tracking Template

### When to Use

Create an Evidence Tracking issue for:
- Each document (email, letter, contract, etc.)
- Each photograph or set of related photos
- Each video or audio recording
- Each physical object
- Each witness statement
- Each expert report

**Rule of Thumb:** If it can prove or disprove a fact, it's evidence and needs tracking.

### What to Include

**Complete Description:**
- What the evidence is
- What it shows or proves
- When it was created/obtained
- Who created it
- Why it matters

**Chain of Custody:**
- When obtained
- Who obtained it
- From whom/where
- Where currently stored
- Who has accessed it
- Any copies made

**Authentication:**
- How you know it's genuine
- Who can verify authenticity
- Original vs. copy
- Metadata available

### Types of Evidence to Track

**Documentary:**
- Contracts and agreements
- Emails and letters
- Text messages
- Memos and notes
- Policies and procedures
- Business records
- Financial documents
- Official records

**Digital:**
- Electronic communications
- Social media posts/messages
- Digital photos
- Audio/video recordings
- Computer files
- Website archives
- Metadata

**Physical:**
- Objects
- Damaged property
- Products
- Original signed documents
- Physical media (CDs, USB drives)

**Testimonial:**
- Witness statements (written)
- Affidavits
- Declarations
- Interview notes

### File Storage Best Practices

**Naming Convention:**
```
EV-[ID]_[DATE]_[TYPE]_[DESCRIPTION].[ext]

Examples:
EV-001_2024-01-15_EMAIL_Termination-Notice.pdf
EV-002_2024-01-20_PHOTO_Property-Damage.jpg
EV-003_2024-02-01_AUDIO_Witness-Interview.mp3
```

**Storage Location:**
```
docs/evidence/case-[name]/[category]/

Examples:
docs/evidence/case-001-employment/emails/
docs/evidence/case-001-employment/photos/
docs/evidence/case-002-contract/documents/
```

**Security:**
- Encrypt sensitive files
- Backup in multiple locations
- Limit access appropriately
- Track who accesses what

## Damages Claim Template

### When to Use

Create a Damages Claim issue for each distinct category of damages:
- Medical expenses
- Lost wages/income
- Property damage
- Out-of-pocket expenses
- Pain and suffering
- Emotional distress
- Loss of enjoyment of life
- Reputational harm

**Note:** Create separate issues for major categories, but you can group similar minor items.

### What to Include

**Economic Damages (Money):**
- Exact amounts with documentation
- Receipts, bills, invoices
- Pay stubs, tax returns
- Repair estimates
- Expert valuations

**Non-Economic Damages:**
- Detailed description of harm
- Impact on daily life
- Duration (ongoing or resolved)
- Treatment received
- Expert opinions (medical, psychological)

**Documentation:**
- Support every claim with evidence
- Link to Evidence Tracking issues
- Provide detailed breakdowns
- Update as damages continue

### Calculating Damages

**Medical Expenses:**
```
Emergency care:        $X,XXX
Hospital stay:         $X,XXX
Doctor visits:         $XXX
Medications:          $XXX
Physical therapy:     $X,XXX
Future treatment:     $X,XXX (estimated)
-----------------------------------
Total Medical:        $XX,XXX
```

**Lost Income:**
```
Days missed:          XX days
Daily rate:           $XXX
Total lost wages:     $X,XXX

Future earning loss:  $XX,XXX (if applicable)
Lost opportunities:   $X,XXX (if applicable)
-----------------------------------
Total Lost Income:    $XX,XXX
```

**Property Damage:**
```
Item 1:
  Original value:     $XXX
  Repair cost:        $XXX
  Replacement cost:   $XXX
  Depreciation:       $XX

Item 2: [same structure]
-----------------------------------
Total Property:       $X,XXX
```

### Non-Economic Damages

**Pain and Suffering:**
- Physical pain levels and duration
- Impact on daily activities
- Medical treatment required
- Permanent effects

**Emotional Distress:**
- Symptoms (anxiety, depression, PTSD, etc.)
- Professional treatment received
- Impact on relationships
- Impact on work/life

**Loss of Enjoyment:**
- Activities no longer possible
- Hobbies affected
- Quality of life changes
- Social impacts

## Timeline Entry Template

### When to Use

Create Timeline Entry issues for:
- Significant events in the case
- Communications (meetings, calls, emails)
- Legal actions taken
- Deadlines and important dates
- Evidence obtained
- Witness interactions
- Any event that will matter to the case

**Note:** Be comprehensive. It's better to have too many timeline entries than to miss important events.

### What to Include

**Precise Timing:**
- Date (YYYY-MM-DD)
- Time if known (HH:MM with timezone)
- Duration if relevant

**Complete Description:**
- What happened
- Who was involved
- Where it occurred
- What was said or done
- What resulted

**Context:**
- Why this event matters
- How it relates to other events
- What it proves or shows

**Evidence:**
- Link to related evidence
- Link to incident reports
- Link to previous/next timeline events

### Creating Connected Timeline

**Link Entries:**
```
Timeline Entry #5: Initial complaint filed
  → Previous: #4 (demand letter sent)
  → Next: #6 (defendant's response received)
  → Related: #2 (incident that prompted complaint)
  → Evidence: #15, #16, #17
```

**Maintain Chronological Order:**
- Create entries as events occur when possible
- Fill in past events systematically
- Verify dates before recording
- Note when exact timing is uncertain

### Timeline Categories

Tag entries by type:
- **Incident** - Harmful events
- **Communication** - Emails, calls, meetings
- **Legal Action** - Filings, hearings, deadlines
- **Financial** - Payments, losses
- **Evidence** - When evidence obtained
- **Administrative** - Non-legal actions

## Best Practices Across All Templates

### Do's ✓

- **Create immediately** - Don't rely on memory
- **Be detailed** - Include everything
- **Be factual** - Objective facts only
- **Link liberally** - Connect related issues
- **Update regularly** - Add new information
- **Use labels** - Tag appropriately
- **Cross-reference** - Link to related items
- **Date consistently** - Always YYYY-MM-DD format

### Don'ts ✗

- **Don't delay** - Document as it happens
- **Don't editorialize** - No opinions in factual issues
- **Don't destroy** - Preserve all evidence
- **Don't guess** - Note uncertainty
- **Don't exaggerate** - Stick to facts
- **Don't omit negatives** - Document unfavorable facts too
- **Don't forget links** - Connect related materials

## Issue Management

### Labels to Use

Standard labels:
- `incident` - Incident reports
- `evidence` - Evidence tracking
- `damages` - Damages claims
- `timeline` - Timeline entries
- `urgent` - Time-sensitive matters
- `verified` - Confirmed information
- `needs-review` - Requires attention
- `incomplete` - Missing information

### Milestones

Consider creating milestones for:
- Pre-litigation preparation
- Discovery period
- Settlement negotiations
- Trial preparation
- Appeal

### Projects

Use GitHub Projects to organize:
- By case (if multiple cases)
- By status (to do, in progress, complete)
- By priority (urgent, important, routine)

## Examples

See actual example issues in the repository for reference on proper completion of each template.

---

**Remember:** These templates are tools to help you document thoroughly and professionally. Use them consistently, update them regularly, and they will help you build a strong, well-documented case.

---

**Last Updated:** 2024-12-11
