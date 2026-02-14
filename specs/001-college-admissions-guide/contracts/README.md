# Spreadsheet Structure Specifications

**Feature**: 001-college-admissions-guide
**Purpose**: Define the structure for the deadline tracking spreadsheet deliverable

---

## Overview

This directory contains specifications for the multi-tab Excel/Google Sheets workbook that will accompany the college admissions guide. The spreadsheet provides organized deadline tracking from multiple perspectives (by university and by career interest).

---

## Template Files

### 1. [university-tab-template.md](university-tab-template.md)
**Purpose**: Structure for each of the 8 university-specific tabs

**Tabs using this template**:
- NC State
- Duke
- UCLA
- App State
- NC A&T
- Georgia Tech
- UNC Charlotte
- UNC Chapel Hill

**Key Features**:
- Track all deadlines for a specific university
- Organized by category (Testing, Application, Essays, Financial Aid, etc.)
- Status tracking and conditional formatting
- Priority levels for critical deadlines

---

### 2. [career-tab-template.md](career-tab-template.md)
**Purpose**: Structure for each of the 7 career interest tabs

**Tabs using this template**:
- Business
- Industrial Design
- Architecture
- Art
- Music Production
- Film Production
- Aerospace Engineering

**Key Features**:
- Shows which universities offer programs for each career
- Program names and deadlines by university
- Additional requirements (portfolios, auditions)
- Program strength indicators

---

### 3. [master-timeline-template.md](master-timeline-template.md)
**Purpose**: Consolidated chronological view of ALL deadlines

**Single tab**: Master Timeline

**Key Features**:
- All deadlines from all universities in one chronological list
- Feb 2026 - Aug 2027 timeline
- Filterable by university, category, priority
- Progress tracking and completion statistics
- Urgent deadline highlighting

---

## Workbook Structure

**Total tabs**: 16
- 8 university tabs
- 7 career interest tabs
- 1 master timeline tab

**Tab order**:
1. Master Timeline (always first for quick reference)
2. University tabs (alphabetically: App State, Duke, Georgia Tech, NC A&T, NC State, UCLA, UNC Chapel Hill, UNC Charlotte)
3. Career tabs (alphabetically: Aerospace Engineering, Architecture, Art, Business, Film Production, Industrial Design, Music Production)

---

## Common Features Across All Tabs

### Conditional Formatting
- **Overdue**: Red highlighting for missed deadlines
- **Upcoming**: Yellow highlighting for deadlines within 2 weeks
- **Completed**: Gray strikethrough for finished tasks
- **Critical**: Bold red font for highest priority items

### Data Validation
- Dropdown menus for consistent data entry
- Date format validation (MM/DD/YYYY)
- Status options: Not Started, In Progress, Completed, Not Applicable

### Navigation
- Freeze panes (header rows stay visible when scrolling)
- Filter buttons enabled on all header rows
- Cross-reference links between tabs

### Printing
- Professional formatting for printing
- Page breaks at logical points
- Headers repeat on each printed page

---

## Implementation Notes

### Excel-Specific Features
- Conditional formatting rules
- Data validation lists
- Formulas for auto-calculations (Days Until, summaries)
- Subtotals and grouping (master timeline)

### Google Sheets Considerations
- Most Excel features translate directly
- Named ranges may be needed for dropdown lists
- Sharing and collaboration features available
- Can use Google Apps Script for advanced automation

---

## Usage Workflow

1. **Master Timeline**: Start here for weekly/daily deadline checks
2. **University Tabs**: Use when working on specific university applications
3. **Career Tabs**: Use when researching programs or comparing options across schools

**Update Frequency**:
- Master Timeline: Review daily during application season, weekly otherwise
- University Tabs: Update as you complete tasks or learn new deadlines
- Career Tabs: Review when making program decisions, less frequent updates

---

## Quality Assurance

Before delivering the final spreadsheet:

- [ ] All 16 tabs created with correct names
- [ ] All templates applied consistently
- [ ] Formulas working correctly (no #REF or #VALUE errors)
- [ ] Conditional formatting rules applied
- [ ] Data validation dropdowns functional
- [ ] Sample data removed (except example rows if helpful)
- [ ] Cross-reference links working
- [ ] Print settings configured
- [ ] Instructions tab included (optional)

---

## Data Population

Data for the spreadsheet comes from Phase 0 research:
- University deadlines: RT-002 (University Admissions Requirements)
- Testing calendar: RT-003 (SAT/ACT Testing Calendar)
- Financial aid deadlines: RT-004 (Financial Aid Deadlines)
- Program mappings: RT-006 (Program Offerings at Target Universities)

**Verification**: All dates must be verified against official sources before populating spreadsheet.

---

## Future Enhancements (Post-Delivery)

Potential improvements for future versions:
- Auto-sync with official university deadlines (API integration)
- Email/SMS reminders for upcoming deadlines
- Mobile app for deadline tracking on-the-go
- Integration with calendar apps (Google Calendar, iCal)
- Automated completion tracking from application portals

---

**Last Updated**: 2026-02-13
**Version**: 1.0
