# Update AI Automation CRM
---
description: Update contact record with feedback and trigger automation improvements
allowed_tools: [Read, Edit, Write, Grep, LS, Task]
---

Update CRM record for contact: $ARGUMENTS

Format: `update-crm "Contact Name" "Feedback or update text"`

1. **Find Contact:**
   - Search CRM directory for matching contact file
   - Display available contacts if not found
   - Load existing contact record

2. **Update Contact Record:**
   - Add new feedback entry with current date
   - Update "Last Updated" timestamp
   - Log feedback in "Feedback History" section with priority level
   - Set follow-up status and next contact date

3. **Process Feedback:**
   - Analyze feedback for automation improvement opportunities
   - Determine if automation documentation needs updates
   - Identify high/medium/low priority changes
   - Create implementation notes

4. **Follow-up Actions:**
   - Update Follow-up Dashboard.md with new status
   - Add action items to contact file if needed
   - Update CRM Overview.md engagement level if changed
   - Set reminder for automation documentation updates

5. **Output Summary:**
   - Confirm contact record updated
   - List any automation improvements identified
   - Show next follow-up date and recommended actions
   - Provide path to updated contact file

**Usage Examples:**
- `update-crm "Sean" "Loves patient scheduling but wants SMS integration"`
- `update-crm "Ultra" "HR onboarding automation saved 5 hours per week"`
- `update-crm "Vito" "Code review automation too complex, needs simplification"`