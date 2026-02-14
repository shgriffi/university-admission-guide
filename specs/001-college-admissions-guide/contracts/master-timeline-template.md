# Master Timeline Tab Template

**Purpose**: Consolidated chronological view of ALL critical dates across all 8 universities from February 2026 through August 2027

**Tab Name**: Master Timeline

---

## Column Structure

| Column | Name | Type | Description | Validation Rules |
|--------|------|------|-------------|------------------|
| A | Date | Date | When the task/deadline occurs | Date format MM/DD/YYYY, sorted ascending |
| B | Month/Year | Text | Grouping helper | Auto-calculated from Date: =TEXT(A2,"MMMM YYYY") |
| C | Days Until | Number | Days from today | Auto-calculated: =A2-TODAY() |
| D | University/Scope | Dropdown | Which university or "All" | Dropdown: NC State, Duke, UCLA, App State, NC A&T, Georgia Tech, UNC Charlotte, UNC Chapel Hill, All Universities, General |
| E | Category | Dropdown | Type of task | Dropdown: Testing, Application, Essays, Supplements, Financial Aid, Decision, Visit, Enrollment, Career Research, Other |
| F | Task/Milestone | Text | Description of what needs to happen | Required, max 200 chars |
| G | Deadline Type | Dropdown | Application timeline | Dropdown: Early Action, Early Decision, Regular Decision, Rolling, General, N/A |
| H | Status | Dropdown | Current completion status | Dropdown: Not Started, In Progress, Completed, Not Applicable |
| I | Priority | Dropdown | Importance level | Dropdown: Critical, High, Medium, Low |
| J | Responsible | Dropdown | Who handles this | Dropdown: Connor, Parents, Both, School Counselor |
| K | Notes/Link | Text | Additional context or hyperlink | Optional, max 500 chars |

---

## Row Content (Chronologically Ordered)

Timeline spans: **February 2026 - August 2027** (18 months)

Includes ALL deadlines from:
- All 8 university tabs
- General testing deadlines (SAT, ACT)
- Financial aid deadlines (FAFSA, CSS Profile)
- Visit planning milestones
- General admissions milestones

**Estimated row count**: 150-300 rows (depending on detail level)

---

## Grouping and Organization

### Option 1: Subtotals by Month
Use Excel subtotals or grouping to create collapsible month sections:
- February 2026
- March 2026
- April 2026
- ... through August 2027

### Option 2: Month Headers
Insert non-data rows with month headers between date groups for visual separation

**Recommended**: Option 1 (subtotals) for better filtering and sorting

---

## Conditional Formatting

**Overdue Items** (Date < TODAY() AND Status ≠ "Completed"):
- Background: Dark red (#CC0000)
- Font: Bold white
- Alert: Immediate action required

**This Week** (Date within 7 days AND Status ≠ "Completed"):
- Background: Orange (#FFAA00)
- Font: Bold black
- Alert: Urgent

**This Month** (Date within 30 days AND Status ≠ "Completed"):
- Background: Light yellow (#FFFFCC)
- Font: Normal black
- Alert: Coming up soon

**Completed Items** (Status = "Completed"):
- Background: Light green (#CCFFCC)
- Font: Strikethrough gray (#999999)

**Critical Priority** (Priority = "Critical" AND Status ≠ "Completed" AND Date < 30 days):
- Border: Thick red border
- Font: Bold dark red

---

## Default Sort and Filter

**Default Sort**:
- Primary: Date (ascending - soonest first)
- Secondary: Priority (Critical > High > Medium > Low)
- Tertiary: University (alphabetical)

**Quick Filters** (predefined filter views):
1. **This Month**: Date within 30 days, Status ≠ "Completed"
2. **Critical Only**: Priority = "Critical", Status ≠ "Completed"
3. **By University**: Filter by specific university
4. **Testing Only**: Category = "Testing"
5. **Applications Only**: Category = "Application"
6. **Financial Aid Only**: Category = "Financial Aid"

---

## Freeze Panes

Freeze first two rows:
- Row 1: Header row
- Row 2: Summary statistics row (see below)

---

## Summary Statistics (Row 2, above data)

| Metric | Formula | Display |
|--------|---------|---------|
| Total Tasks | =COUNTA(F:F)-2 | 237 tasks |
| Completed | =COUNTIF(H:H,"Completed") | 45 completed (19%) |
| Overdue | =COUNTIFS(A:A,"<"&TODAY(),H:H,"<>Completed") | 3 OVERDUE! |
| Next Deadline | =MIN(IF(H:H<>"Completed",A:A)) | 02/25/2026 (3 days) |
| Critical Pending | =COUNTIFS(I:I,"Critical",H:H,"<>Completed") | 8 critical tasks |

---

## Example Data Rows

| Date | Month/Year | Days Until | University/Scope | Category | Task/Milestone | Deadline Type | Status | Priority | Responsible | Notes/Link |
|------|------------|------------|------------------|----------|----------------|---------------|--------|----------|-------------|------------|
| 02/15/2026 | February 2026 | -3 | General | Career Research | Complete career path research | N/A | Completed | Medium | Connor | Read all 7 career guides in main document |
| 03/08/2026 | March 2026 | 23 | All Universities | Testing | SAT Test Date (March administration) | N/A | Not Started | High | Connor | Register by 02/07/2026 |
| 04/15/2026 | April 2026 | 61 | Duke | Visit | Schedule Duke campus tour | N/A | Not Started | Medium | Both | Book for junior spring visit |
| 05/01/2026 | May 2026 | 77 | All Universities | Application | Common App opens for 2026-27 cycle | N/A | Not Started | Low | Connor | Create account, start exploring |
| 06/15/2026 | June 2026 | 122 | Connor | Career Research | Narrow career interests to top 3 | N/A | Not Started | High | Connor | Discuss with parents and counselor |
| 09/05/2026 | September 2026 | 204 | All Universities | Testing | Register for October SAT | N/A | Not Started | Critical | Connor | LAST test date for Early Action deadlines! |
| 10/01/2026 | October 2026 | 230 | All Universities | Financial Aid | FAFSA opens | General | Not Started | Critical | Parents | Complete ASAP for priority consideration |
| 10/15/2026 | October 2026 | 244 | NC State | Application | NC State Early Action deadline | Early Action | Not Started | Critical | Connor | Submit complete application by 11:59 PM |
| 11/01/2026 | November 2026 | 261 | Duke | Application | Duke Early Decision deadline | Early Decision | Not Started | Critical | Connor | BINDING - only apply if Duke is #1 choice |
| 11/01/2026 | November 2026 | 261 | UNC Chapel Hill | Application | UNC Early Action deadline | Early Action | Not Started | Critical | Connor | In-state applicant advantage |
| 11/30/2026 | November 2026 | 290 | UCLA | Application | UC Application deadline | Regular Decision | Not Started | Critical | Connor | All UC schools use same application |
| 01/02/2027 | January 2027 | 323 | Duke | Application | Duke Regular Decision deadline | Regular Decision | Not Started | High | Connor | If not applying Early Decision |
| 01/30/2027 | January 2027 | 351 | NC State | Decision | NC State EA decision notification | Early Action | Not Started | Medium | Connor | Check portal, decision by email |
| 03/25/2027 | March 2027 | 405 | UCLA | Decision | UC decision notifications | Regular Decision | Not Started | Medium | Connor | All UC schools notify same day |
| 05/01/2027 | May 2027 | 442 | All Universities | Enrollment | National Decision Day | General | Not Started | Critical | Connor | Commit to one university, submit deposit |
| 08/15/2027 | August 2027 | 548 | [Selected University] | Enrollment | Move-in day / Orientation begins | General | Not Started | High | Both | Start of college! |

---

## Additional Features

### 1. Progress Tracking
- Add sparkline chart showing completion trend over time
- Calculate percentage complete by month
- Visual progress bar for overall completion

### 2. Milestone Markers
Insert special rows for major milestones:
- Start of senior year (August 2026)
- Application season begins (September 2026)
- Early decision deadline window (November 2026)
- Regular decision deadline window (January 2027)
- Decision notification period (March-April 2027)
- National Decision Day (May 1, 2027)
- High school graduation (June 2027)
- College enrollment (August 2027)

### 3. Color-Coded Rows by Category
Use subtle background colors for quick scanning:
- Testing: Light blue (#E6F2FF)
- Application: Light orange (#FFE6CC)
- Financial Aid: Light green (#E6FFE6)
- Decisions: Light purple (#F2E6FF)
- Visits: Light yellow (#FFFACD)

### 4. Notes Column Enhancements
- Hyperlinks to university application portals
- Links to specific sections in main guide document
- Links to university tabs in spreadsheet for more details

---

## Print Settings

- Orientation: Portrait
- Scaling: Fit all columns on one page width (multiple pages length OK)
- Print titles: Repeat header row on each page
- Page breaks: Insert after each month grouping (optional)

---

## Maintenance Notes

- When a task is completed, update Status to "Completed" immediately
- New deadlines can be added at any time - table will auto-sort by date
- Review and update this tab weekly during application season (Aug 2026 - Jan 2027)
- Cross-check with university tabs monthly to ensure consistency
- Archive or hide completed tasks after decisions are final (May 2027)

---

## Data Sources

This tab consolidates data from:
- All 8 university-specific tabs
- College Board SAT calendar
- ACT test calendar
- FAFSA/CSS Profile deadlines
- General admissions milestones

**Maintenance**: When updating a deadline in a university tab, also update it here in the master timeline for consistency.

**Alternative**: Use formulas to pull dates from university tabs automatically (advanced Excel users)

---

**Last Updated**: 2026-02-13
**Template Version**: 1.0
