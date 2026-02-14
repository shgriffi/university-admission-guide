# University Tab Template

**Purpose**: Structure for each of the 8 university-specific spreadsheet tabs

**Tab Names**:
- NC State
- Duke
- UCLA
- App State
- NC A&T
- Georgia Tech
- UNC Charlotte
- UNC Chapel Hill

---

## Column Structure

| Column | Name | Type | Description | Validation Rules |
|--------|------|------|-------------|------------------|
| A | Task/Milestone | Text | Specific action or deadline item | Required, max 200 chars |
| B | Date | Date | Target date for task/milestone | Date format MM/DD/YYYY |
| C | Category | Dropdown | Type of task | Dropdown: Testing, Application, Essays, Supplements, Financial Aid, Decision, Visit, Enrollment, Other |
| D | Deadline Type | Dropdown | Application timeline type | Dropdown: Early Action, Early Decision, Regular Decision, Rolling, N/A |
| E | Status | Dropdown | Current completion status | Dropdown: Not Started, In Progress, Completed, Not Applicable |
| F | Priority | Dropdown | Importance level | Dropdown: Critical, High, Medium, Low |
| G | Notes | Text | Additional details, links, context | Optional, max 500 chars |
| H | Responsible | Text | Who is handling this task | Dropdown: Connor, Parents, Both, School Counselor |

---

## Row Categories (Suggested Groupings)

### Testing Section
- SAT/ACT registration deadlines
- Test dates
- Score send deadlines
- Subject test requirements (if applicable for homeschoolers)

### Application Section
- Application opens
- Application deadline (by type: EA/ED/RD)
- Application fee payment
- Transcript submission
- School report submission

### Essays & Supplements Section
- Common App essay
- Supplemental essays (list each)
- Portfolio submissions (for art/design/architecture)
- Additional writing samples

### Financial Aid Section
- FAFSA deadline
- CSS Profile deadline
- University-specific financial aid forms
- Scholarship application deadlines

### Decision Section
- Decision notification date (by application type)
- Response deadline (if accepted)
- Deposit deadline

### Visit Section
- Tour registration
- Visit date
- Information session
- Overnight program (if applicable)

### Enrollment Section
- Enrollment confirmation
- Housing application
- Orientation registration
- Course registration

---

## Conditional Formatting

**Overdue Items** (Date < TODAY() AND Status ≠ "Completed"):
- Background: Light red (#FFCCCC)
- Font: Bold

**Upcoming Items** (Date within 14 days AND Status ≠ "Completed"):
- Background: Light yellow (#FFFFCC)
- Font: Normal

**Completed Items** (Status = "Completed"):
- Background: Light gray (#EEEEEE)
- Font: Strikethrough
- Text color: Gray (#999999)

**Critical Priority** (Priority = "Critical" AND Status ≠ "Completed"):
- Font: Bold
- Text color: Dark red (#CC0000)

---

## Default Sort Order

Primary: Date (ascending)
Secondary: Priority (Critical > High > Medium > Low)

---

## Freeze Panes

Freeze first row (header row) for scrolling

---

## Example Data

| Task/Milestone | Date | Category | Deadline Type | Status | Priority | Notes | Responsible |
|----------------|------|----------|---------------|--------|----------|-------|-------------|
| Register for October SAT | 09/05/2026 | Testing | N/A | Not Started | Critical | Last test date for Early Action | Connor |
| Submit Common App | 11/01/2026 | Application | Early Action | Not Started | Critical | NC State EA deadline | Connor |
| Complete supplemental essay | 10/25/2026 | Essays | Early Action | Not Started | High | "Why NC State?" 300 words | Connor |
| Submit FAFSA | 11/15/2026 | Financial Aid | Early Action | Not Started | Critical | NC State priority deadline | Parents |
| Decision notification | 01/30/2027 | Decision | Early Action | Not Started | Medium | Check portal after this date | Connor |

---

## Tab-Specific Customization

Each university tab should include:
1. **Header section** (above column headers):
   - University name and logo (if available)
   - Admissions office contact: phone, email, website
   - Application platform used (Common App, Coalition, university-specific)

2. **Summary section** (below data rows):
   - Total tasks: COUNT of all rows
   - Completed: COUNT of "Completed" status
   - Overdue: COUNT of overdue items
   - Next deadline: MIN date where Status ≠ "Completed"

---

## Notes for Implementation

- Protect structure (lock columns and formatting) while allowing data entry
- Include filter buttons on header row
- Validate dropdown selections to prevent typos
- Use data validation for date fields to ensure proper format
- Consider adding hyperlinks in Notes column for direct access to university portals
- Print settings: Landscape orientation, fit to 1 page wide

---

**Last Updated**: 2026-02-13
**Template Version**: 1.0
