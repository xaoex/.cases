# Guide: Creating Your First Case

This guide walks you through setting up comprehensive documentation for a new legal case using this repository system.

## Before You Begin

### What You Need
- [ ] Understanding of the situation/problem
- [ ] Any evidence already in your possession
- [ ] Timeline of key events (approximate is okay)
- [ ] Documentation of any damages/losses
- [ ] Contact information for witnesses (if any)
- [ ] Consultation scheduled with legal counsel

### Important Reminders
⚠️ **Consult with a lawyer** - This system helps organize, but legal advice requires an attorney
⚠️ **Preserve evidence** - Don't destroy anything that might be relevant
⚠️ **Track deadlines** - Note any statute of limitations or filing deadlines
⚠️ **Be thorough** - Document everything, even if you're not sure it matters

## Step 1: Create Your First Incident Report

### 1.1 Navigate to Issues
1. Click the **Issues** tab in this repository
2. Click the green **New Issue** button
3. Select the **Incident Report** template

### 1.2 Fill Out the Template

**Incident Information Section:**
- **Incident ID:** Give it a unique identifier (e.g., INC-001)
- **Date of Incident:** Use YYYY-MM-DD format (e.g., 2024-01-15)
- **Time of Incident:** Include timezone if known (e.g., 14:30 EST)
- **Location:** Be as specific as possible

**Description Section:**
- **What Happened:** Write a clear, factual description
  - Who was involved?
  - What did they do or say?
  - What happened as a result?
  - Be objective - stick to facts, not opinions
  
**Example:**
```
On January 15, 2024, at approximately 2:30 PM, I met with John Smith 
at his office located at 123 Main St. During this meeting, Mr. Smith 
informed me that the contract was being terminated effective immediately. 
I requested an explanation, but Mr. Smith refused to provide one and 
asked me to leave the premises.
```

**Parties Involved:**
- List everyone who was present or involved
- Include names, roles, and relationships
- Note anyone who witnessed the event

**Impact Assessment:**
- Describe what happened as a result
- Note any immediate harm or loss
- Describe ongoing effects
- Estimate financial impact if possible

**Evidence:**
- Check boxes for types of evidence you have
- List specific evidence items (you'll create detailed tracking later)

**Legal Relevance:**
- Note any laws or agreements you believe were violated
- You can leave this section for legal counsel to help complete

### 1.3 Submit the Issue
1. Add labels (e.g., `incident`, `urgent` if time-sensitive)
2. Click **Submit new issue**
3. Note the issue number (e.g., #1) for future reference

## Step 2: Create Evidence Tracking Issues

For each piece of evidence you have (or will obtain):

### 2.1 Create Evidence Issue
1. Go to Issues → New Issue
2. Select **Evidence Tracking** template
3. Fill out for each distinct piece of evidence

### 2.2 Evidence Examples

**Documentary Evidence:**
- Emails → Create one issue per email or email thread
- Contracts → One issue per document
- Letters → One issue per letter
- Text messages → Can group conversation threads

**Digital Evidence:**
- Photos → One issue per photo or related set
- Videos → One issue per video
- Audio recordings → One issue per recording
- Screenshots → Group related screenshots

**Physical Evidence:**
- Objects → One issue per item
- Damaged property → One issue, with photos

### 2.3 Store Evidence Files

**For Digital Evidence:**
1. Create directory: `docs/evidence/case-[your-case-name]/`
2. Save files with descriptive names:
   ```
   EV-001_2024-01-15_EMAIL_Contract-Termination.pdf
   EV-002_2024-01-20_PHOTO_Damaged-Property.jpg
   ```
3. Link file paths in the Evidence Tracking issue

**For Physical Evidence:**
- Store securely
- Take photographs
- Note storage location in the issue
- Upload photos to repository

### 2.4 Link Evidence to Incident
- In the Evidence Tracking issue, reference the related Incident Report
- In the Incident Report, edit to link to Evidence issues

## Step 3: Build Your Timeline

### 3.1 List Key Events

Start by listing all significant events chronologically:
- First contact or interaction
- Agreement or contract signed
- Problems began
- Communications about problems
- Harmful events
- Your responses
- Their responses
- Current status

### 3.2 Create Timeline Entry Issues

For each significant event:
1. Create new issue with **Timeline Entry** template
2. Fill in date, time, description
3. Link to related incidents and evidence
4. Link to previous/next timeline entries

### 3.3 Example Timeline Entries

```
Timeline Entry 1:
Date: 2023-06-01
Event: Initial contract signed
Evidence: #5 (contract document)

Timeline Entry 2:
Date: 2023-12-01
Event: First complained about issue
Evidence: #6 (email to defendant)

Timeline Entry 3:
Date: 2024-01-15
Event: Contract terminated without cause
Related: #1 (incident report)
Evidence: #7 (termination letter)
```

## Step 4: Document Damages

### 4.1 Identify Damage Categories

**Economic Damages (Money):**
- Lost income/wages
- Medical expenses
- Property damage/repair costs
- Out-of-pocket expenses
- Loss of business opportunity
- Other financial losses

**Non-Economic Damages (Non-monetary):**
- Pain and suffering
- Emotional distress
- Loss of enjoyment of life
- Reputational harm
- Loss of relationships

### 4.2 Create Damages Claim Issues

Create separate issues for each major category:
1. One for "Economic Damages - Medical"
2. One for "Economic Damages - Lost Income"
3. One for "Non-Economic Damages - Emotional Distress"
4. Etc.

### 4.3 Support With Documentation

For each damages claim:
- Attach receipts, bills, invoices
- Include pay stubs or tax returns
- Provide medical records
- Get expert valuations
- Document with photos
- Keep detailed records

## Step 5: Create Your Case File

### 5.1 Create Case Directory
```bash
mkdir -p docs/cases/case-001-[brief-description]
cd docs/cases/case-001-[brief-description]
```

### 5.2 Create Case Overview Document

Create file: `00-case-overview.md`

Use the template from `docs/cases/README.md` and fill in:
- Case identification information
- Executive summary (2-3 paragraphs)
- Key dates
- Parties involved
- Claims/causes of action
- Damages summary
- Case strengths and challenges

### 5.3 Create Additional Case Documents

Based on templates in `docs/cases/README.md`, create:
- `01-parties.md` - Details on all parties
- `02-facts.md` - Complete statement of facts
- `03-timeline.md` - Compiled timeline narrative
- `04-evidence-index.md` - Master evidence list
- `05-damages.md` - Complete damages calculation

You don't need to complete all of these immediately. Start with the overview and build out as you develop the case.

## Step 6: Review and Organize

### 6.1 Cross-Reference Everything

Verify that:
- [ ] All incident reports link to relevant evidence
- [ ] All evidence links back to incidents
- [ ] Timeline entries link to both incidents and evidence
- [ ] Damages claims link to supporting evidence
- [ ] Case file references all issue numbers

### 6.2 Check Completeness

Review for gaps:
- [ ] Missing dates or times?
- [ ] Unidentified parties or witnesses?
- [ ] Evidence you know exists but haven't tracked?
- [ ] Events you remember but haven't documented?
- [ ] Damages you haven't calculated?

### 6.3 Verify Accuracy

Double-check:
- [ ] All dates are correct
- [ ] Names are spelled correctly
- [ ] Amounts are accurate
- [ ] Facts are objective (not opinions)
- [ ] Timeline is in correct order

## Step 7: Prepare for Legal Consultation

### 7.1 Create Summary Package

Prepare for attorney meeting:
1. Print or export the case overview
2. Create list of all GitHub issues
3. Prepare evidence index
4. Print or export timeline
5. Compile damages summary

### 7.2 Prepare Questions

List questions for your attorney:
- Legal merit of claims?
- Statute of limitations?
- Likely outcomes?
- Costs and timeline?
- Settlement prospects?
- What additional evidence needed?

### 7.3 During the Meeting

- Share the organized materials
- Walk through the timeline
- Discuss each incident
- Review evidence
- Get advice on legal strategy
- Ask about missing information
- Discuss next steps

### 7.4 After the Meeting

- Update documentation based on attorney feedback
- Add any new information discovered
- Complete any tasks assigned
- Follow attorney's advice on legal strategy
- Continue maintaining the system

## Step 8: Ongoing Maintenance

### 8.1 As Events Occur

- Create new Incident Reports immediately
- Add new Evidence Tracking issues as evidence obtained
- Update Timeline with new entries
- Update Damages Claims as losses continue
- Keep everything current

### 8.2 Regular Reviews

**Weekly:**
- Review all open issues
- Update any with new information
- Check that everything is linked properly

**Monthly:**
- Comprehensive review of case file
- Update formal documentation
- Verify accuracy and completeness
- Backup all materials

## Common Mistakes to Avoid

❌ **Waiting too long** - Document events as they happen
❌ **Being incomplete** - Include all details, even if uncertain of relevance
❌ **Being subjective** - Stick to facts, not interpretations
❌ **Poor organization** - Use the templates and structure
❌ **Missing evidence** - Collect and preserve everything
❌ **Ignoring deadlines** - Track statute of limitations carefully
❌ **Going without lawyer** - Always consult qualified legal counsel

## Checklist: First Case Setup Complete

- [ ] Created at least one Incident Report
- [ ] Created Evidence Tracking issues for available evidence
- [ ] Started Timeline with key events
- [ ] Documented known Damages
- [ ] Created case directory and overview
- [ ] Cross-referenced all issues and documents
- [ ] Reviewed for completeness and accuracy
- [ ] Scheduled or completed consultation with attorney
- [ ] Set up regular review schedule
- [ ] Backed up all materials

## What's Next?

After completing initial setup:

1. **Continue Documentation** - Add new issues as events occur
2. **Develop Case File** - Complete all case documents
3. **Work with Attorney** - Follow legal counsel's guidance
4. **Maintain System** - Regular updates and reviews
5. **Prepare for Proceedings** - Organize for court as case develops

## Getting Help

**Stuck on something?**
- Review the [How to Use Guide](./01-how-to-use.md)
- Check specific section README files
- Review issue templates for guidance
- Consult with legal counsel for legal questions

**Not sure if something is important?**
- Document it anyway
- Let attorney assess relevance
- Better to have too much than too little

---

**Remember:** This system is most effective when kept current. Document as events occur, review regularly, and work closely with your legal counsel.

---

**Last Updated:** 2024-12-11
