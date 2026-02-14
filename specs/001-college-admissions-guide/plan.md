# Implementation Plan: Connor's Comprehensive College Admissions Guide

**Branch**: `001-college-admissions-guide` | **Date**: 2026-02-13 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/001-college-admissions-guide/spec.md`

## Summary

Create a comprehensive college admissions guide for homeschooled student Connor Griffin (17, 11th grade) covering his college application journey from February 2026 through enrollment in August 2027. The guide addresses 8 target universities (NC State, Duke, UCLA, App State, NC A&T, Georgia Tech, UNC Charlotte, UNC Chapel Hill) and 7 potential career paths (business, industrial design, architecture, art, music production, film production, aerospace engineering).

**Core Deliverables**:
1. **Formatted Document/PDF**: Comprehensive guide with university profiles, career guides, timeline, homeschool-specific requirements, and visit planning instructions
2. **Deadline Tracking Spreadsheet**: 16 CSV files (8 university tabs + 7 career interest tabs + 1 master timeline tab) with instructions for Google Sheets import

**Critical Context**: Connor is homeschooled with parent-calculated GPA, requiring special attention to homeschool-specific admission requirements, transcript preparation, third-party validation, and letters of recommendation across all eight universities.

## Technical Context

**Project Type**: Content/Documentation (guide document + spreadsheet deliverables)
**Content Format**: Markdown source → Microsoft Word → PDF/DOCX output
**Spreadsheet Format**: CSV files (locally stored) → Google Sheets (manual import for family use)
**Document Generation**: Markdown files manually formatted in Microsoft Word, exported to PDF/DOCX
**Primary Dependencies**:
- Document: Microsoft Word (for formatting and export)
- Spreadsheet: CSV files for version control, Google Sheets for family daily use
- Research: Web browsers for accessing official university sources
- Maintenance: Claude/AI for monthly guide updates

**Content Constraints**:
- Reading level: ≤ 10th grade (Flesch-Kincaid ≤ 10.0) per constitution
- All facts must cite authoritative sources with verification dates
- Updates required monthly via AI-assisted process (FR-007a, FR-007b, FR-007c)
- Must be printable and digitally shareable

**Scale/Scope**:
- 8 university profiles (NC State, Duke, UCLA, App State, NC A&T, Georgia Tech, UNC Charlotte, UNC Chapel Hill)
- 7 career path guides (business, industrial design, architecture, art, music production, film production, aerospace engineering)
- 18-month timeline (February 2026 - August 2027)
- 16 CSV files (8 university + 7 career + 1 master timeline)
- Estimated 80-120 pages of guide content
- 150-300 deadline/milestone entries across all spreadsheet tabs

**Quality Targets**:
- 100% of deadline dates accurate as of February 2026
- 100% of information cited from authoritative sources
- Users can locate any specific requirement within 5 minutes
- Users can locate any deadline in spreadsheet within 30 seconds
- Document remains readable when printed (no cut-off content)
- Family can complete monthly AI-assisted updates within 30 minutes (SC-007a)

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

This feature must align with all five core principles from the project constitution:

### ✓ I. Accessibility
- [x] Plain language requirement documented (11th grade reading level in spec)
- [x] Complex processes will be broken into numbered steps (timelines, checklists per FR-006, FR-008)
- [x] Visual aids planned (spreadsheet tabs for organization per FR-003, FR-004)
- [x] No jargon or terms defined on first use (per constitution requirement)

**Status**: PASS - Specification includes appropriate accessibility requirements

### ✓ II. Accuracy
- [x] All facts must cite authoritative sources (FR-019, SC-016)
- [x] Verification dates required (Assumption 6, constitution requirement)
- [x] Monthly update cycle with AI assistance planned (Assumption 4, FR-007a-c)
- [x] Examples marked as realistic (constitution requirement)

**Status**: PASS - Specification mandates rigorous sourcing and verification with AI-assisted monthly updates

### ✓ III. Comprehensiveness
- [x] Timeline spans full admissions cycle (Feb 2026 - Aug 2027 per FR-008, FR-005)
- [x] All required topics covered (testing, applications, financial aid, visits, homeschool requirements)
- [x] Each topic addresses: what, why, when, how (per user stories structure)
- [x] Gaps explicitly documented (User Story 3 focuses on homeschool-specific coverage)

**Status**: PASS - Specification is comprehensive across all required dimensions

### ✓ IV. Actionability
- [x] Checklists and timelines included (FR-006, FR-008, FR-044)
- [x] Month-by-month timeline with specific action items (FR-008)
- [x] Templates provided (FR-022a-c for transcript, FR-038, FR-045 for visit documentation)
- [x] Step-by-step procedures for complex processes (transcript preparation, AI updates)

**Status**: PASS - Templates and procedures clarified (transcript template + sample, AI update instructions)

### ✓ V. Inclusivity
- [x] Homeschool-specific requirements extensively covered (User Story 3, FR-021 through FR-029)
- [x] Multiple career paths addressed (7 different careers from business to engineering)
- [x] Various academic profiles (8 universities ranging from highly selective to safety schools)
- [x] First-generation considerations implicit (guide assumes no prior admissions knowledge per Assumption 7)

**Status**: PASS - Specification centers homeschool family needs and diverse career interests

### Content Standards Compliance
- [x] Chronological organization (timeline-based per FR-005, FR-008)
- [x] Consistent formatting (document with TOC, page numbers per FR-007)
- [x] Cross-references planned (career-to-university mapping per FR-036-FR-041)
- [x] Update tracking (verification dates per Assumption 6, AI update instructions per FR-007a-c)

**Status**: PASS

### Overall Gate Decision: **PASS** ✓

**Post-Clarification Notes**:
- Document generation approach resolved: Markdown → Word → PDF/DOCX
- Spreadsheet format resolved: CSV files with Google Sheets import instructions
- Maintenance approach resolved: AI-assisted monthly updates with specific prompts
- Transcript deliverables resolved: Fillable template + anonymized sample
- Testing strategy resolved: SAT primary with ACT backup

## Project Structure

### Documentation (this feature)

```text
specs/001-college-admissions-guide/
├── plan.md              # This file (/speckit.plan command output)
├── research.md          # Phase 0 output (/speckit.plan command)
├── data-model.md        # Phase 1 output (/speckit.plan command)
├── quickstart.md        # Phase 1 output (/speckit.plan command)
├── contracts/           # Phase 1 output (/speckit.plan command)
│   ├── README.md        # Spreadsheet structure overview
│   ├── university-tab-template.md
│   ├── career-tab-template.md
│   └── master-timeline-template.md
└── tasks.md             # Phase 2 output (/speckit.tasks command - NOT created by /speckit.plan)
```

### Content Structure (repository root)

This is a content/documentation project, not a traditional software project. Structure reflects content organization and outputs.

```text
content/
├── guide/
│   ├── 01-introduction.md         # Overview, how to use guide
│   ├── 02-timeline-overview.md    # Master timeline Feb 2026 - Aug 2027
│   ├── 03-universities/           # University profiles (8 files)
│   │   ├── nc-state.md
│   │   ├── duke.md
│   │   ├── ucla.md
│   │   ├── app-state.md
│   │   ├── nc-at.md
│   │   ├── georgia-tech.md
│   │   ├── unc-charlotte.md
│   │   └── unc-chapel-hill.md
│   ├── 04-homeschool-requirements/ # Homeschool-specific guidance
│   │   ├── overview.md
│   │   ├── transcripts.md
│   │   ├── transcript-template.docx  # Fillable template (FR-022a)
│   │   ├── transcript-sample.pdf     # Anonymized example (FR-022b)
│   │   ├── recommendations.md
│   │   ├── validation.md
│   │   └── nc-regulations.md
│   ├── 05-career-paths/           # Career guides (7 files)
│   │   ├── business.md
│   │   ├── industrial-design.md
│   │   ├── architecture.md
│   │   ├── art.md
│   │   ├── music-production.md
│   │   ├── film-production.md
│   │   └── aerospace-engineering.md
│   ├── 06-career-university-mapping.md  # Which schools offer which programs
│   ├── 07-visit-planning.md       # Campus visit guide
│   ├── 08-ai-update-guide.md      # How to update guide monthly with AI (FR-007a-c)
│   └── 09-appendices.md           # Resources, glossary, sources
│
├── spreadsheets/
│   ├── csv/                        # CSV files for version control
│   │   ├── master-timeline.csv
│   │   ├── nc-state.csv
│   │   ├── duke.csv
│   │   ├── ucla.csv
│   │   ├── app-state.csv
│   │   ├── nc-at.csv
│   │   ├── georgia-tech.csv
│   │   ├── unc-charlotte.csv
│   │   ├── unc-chapel-hill.csv
│   │   ├── business.csv
│   │   ├── industrial-design.csv
│   │   ├── architecture.csv
│   │   ├── art.csv
│   │   ├── music-production.csv
│   │   ├── film-production.csv
│   │   └── aerospace-engineering.csv
│   └── import-instructions.md      # How to import CSVs to Google Sheets (FR-002a)
│
├── output/
│   ├── connor-college-guide.pdf   # Final PDF deliverable
│   └── connor-college-guide.docx  # Final Word doc deliverable
│
└── research/
    ├── sources/                    # Captured university requirements
    │   ├── nc-state-requirements.md
    │   ├── duke-requirements.md
    │   ├── ucla-requirements.md
    │   ├── app-state-requirements.md
    │   ├── nc-at-requirements.md
    │   ├── georgia-tech-requirements.md
    │   ├── unc-charlotte-requirements.md
    │   └── unc-chapel-hill-requirements.md
    ├── testing-calendar.md         # SAT/ACT dates 2026-2027
    ├── financial-aid-deadlines.md  # FAFSA, CSS Profile dates
    └── ai-update-prompts.md        # Prompt templates for monthly updates
```

**Structure Decision**: Content-based organization with modular markdown files that can be assembled into the final document. Each university and career path gets its own file for easier updates and maintenance. CSV files stored separately for version control. Research folder captures raw data from authoritative sources before it's synthesized into guide content.

## Complexity Tracking

> **Fill ONLY if Constitution Check has violations that must be justified**

No violations identified. All constitutional requirements are met by the specification. Post-clarification, all previously unresolved items have been addressed.

---

## Phase 0: Research & Information Gathering

**Objective**: Gather authoritative source data for the guide. All NEEDS CLARIFICATION items have been resolved through the clarification session.

### Research Tasks

#### RT-001: Document Generation Tooling - RESOLVED
**Question**: What tool/process will be used to convert markdown content into formatted PDF/DOCX with TOC, page numbers, and professional layout?

**Decision** (from clarification session): Markdown files maintained as source, manually formatted in Microsoft Word, exported to PDF/DOCX

**Rationale**:
- Provides maximum control over professional formatting
- Accessible to family for future updates
- No technical dependencies on conversion tools
- Allows for custom table of contents, page numbers, headers/footers
- Repeatable process for monthly updates

**No further research required** - approach is clear and actionable.

---

#### RT-002: University Admissions Requirements (8 universities)
**Question**: What are the current admissions requirements, deadlines, and homeschool-specific policies for each target university?

**Data to gather for each university**:
- Application deadlines (Early Action, Early Decision, Regular Decision) - specific dates
- Required test scores (SAT/ACT ranges, subject test requirements)
- GPA expectations (middle 50% ranges)
- Essay requirements (number, prompts, word limits)
- Supplemental materials (arts portfolios, additional forms)
- Financial aid deadlines (FAFSA, CSS Profile, institutional forms)
- Homeschool-specific requirements (transcript format, third-party validation, additional testing)
- Decision notification dates
- Application platform (Common App, Coalition, university-specific)
- Contact information for admissions office

**Sources**:
- Official university admissions websites (primary source)
- Common Application portal
- Coalition Application portal
- College Board (for SAT/testing info)
- Individual university homeschool admissions pages

**Output**: 8 university requirement files in `research/sources/`

---

#### RT-003: SAT/ACT Testing Calendar 2026-2027
**Question**: What are all available test dates, registration deadlines, and score release dates for SAT/ACT during the application timeline?

**Data to gather** (prioritize SAT per clarification, include ACT as backup per FR-009a):
- All SAT test dates from March 2026 - December 2026
- Registration deadlines for each test
- Late registration deadlines
- Score release dates
- Which test dates are final opportunities for early action/decision (October 2026)
- Which test dates work for regular decision (December 2026)
- Test center registration process
- ACT test dates and deadlines as backup option
- Decision points for evaluating SAT performance and considering ACT switch (FR-013a)

**Sources**:
- College Board official SAT calendar
- ACT official test calendar

**Output**: `research/testing-calendar.md`

---

#### RT-004: Financial Aid Deadlines and Process
**Question**: What are the FAFSA, CSS Profile, and university-specific financial aid deadlines for 2026-2027 admissions cycle?

**Data to gather**:
- FAFSA opening date (October 1, 2026)
- CSS Profile opening date
- Priority financial aid deadlines for each of 8 universities
- Required financial aid forms by university
- North Carolina state aid programs and deadlines
- Scholarship application deadlines (university-specific merit scholarships)

**Sources**:
- Federal Student Aid (FAFSA) official site
- College Board CSS Profile site
- Each university's financial aid office website
- North Carolina state financial aid programs

**Output**: `research/financial-aid-deadlines.md`

---

#### RT-005: Career Path Research (7 careers)
**Question**: What are the day-to-day realities, required skills, education paths, and job market outlook for each of Connor's 7 potential career paths?

**Data to gather for each career**:
- Clear definition of the career field
- Typical day-to-day work activities (concrete examples)
- Required technical skills
- Required soft skills and personality traits
- Typical career progression (entry → senior roles)
- Educational requirements (degree level, relevant majors, certifications)
- Realistic salary ranges (entry-level and experienced)
- Job market outlook and demand trends (BLS data)
- Work environments (corporate, freelance, agency, etc.)

**Careers to research**:
1. Business (note: broad field - may need to narrow to finance, marketing, management)
2. Industrial Design
3. Architecture
4. Art (visual arts, fine arts)
5. Music Production
6. Film Production
7. Aerospace Engineering

**Sources**:
- Bureau of Labor Statistics (BLS) Occupational Outlook Handbook
- Professional associations (IDSA for industrial design, AIA for architecture, etc.)
- University career services resources
- O*NET Online (Department of Labor career database)
- Industry publications and career guides

**Output**: 7 career research files in `research/career-paths/`

---

#### RT-006: Program Offerings at Target Universities
**Question**: Which of the 8 target universities offer programs relevant to each of Connor's 7 career interests, and what are the specific major names and program strengths?

**Data to gather**:
- Program availability matrix (8 universities × 7 careers = 56 cells)
- Specific major/program names for each career at each university
- Program rankings or reputation indicators
- Unique program features or strengths
- Additional admission requirements (portfolios for art/design/architecture programs)
- Programs that don't exist at certain universities (note alternatives)
- Schools with strongest multi-career flexibility

**Sources**:
- Each university's academic catalog/majors list
- Department websites for specific programs
- U.S. News rankings (if available)
- University admissions pages for competitive programs

**Output**: `research/program-mapping-matrix.md`

---

#### RT-007: North Carolina Homeschool Regulations
**Question**: What are North Carolina's legal requirements for homeschooling that may be referenced in college applications?

**Data to gather**:
- NC homeschool registration requirements
- Required annual testing (if applicable)
- Notification/filing requirements with local education authorities
- Homeschool transcript recommendations from NC homeschool organizations
- NC-specific homeschool documentation that universities might request

**Sources**:
- North Carolina Division of Non-Public Education
- NC Home School Law (NCGS § 115C-563 through 565)
- NC Home Education Association (NCHEA) resources
- Homeschool Legal Defense Association (HSLDA) NC page

**Output**: `research/nc-homeschool-regulations.md`

---

#### RT-008: College Visit Planning Best Practices
**Question**: What are optimal timing, scheduling processes, and best practices for planning productive college visits?

**Data to gather**:
- Optimal visit timing (junior spring vs senior fall, avoiding exam periods)
- How to schedule official tours at each of 8 universities
- Information session availability
- Special visit opportunities (class attendance, overnight stays, department-specific visits)
- Questions to ask during visits
- What to observe and document
- Whether visits impact admission chances (demonstrated interest policies by university)
- Virtual visit options

**Sources**:
- Each university's visit/tour website
- College admissions guidebooks
- College counseling best practices

**Output**: `research/visit-planning-best-practices.md`

---

#### RT-009: AI Update Prompt Templates (NEW - from clarification)
**Question**: What specific prompts and procedures should the family use with Claude/AI to perform monthly guide updates?

**Data to gather**:
- Example prompts for checking university admissions pages for deadline changes
- Prompt templates for extracting updated information from official sources
- Verification checklist of all critical sources (8 university sites, SAT/ACT calendars, FAFSA)
- Instructions for providing URLs to AI for automated checking
- Format for generating updated markdown and CSV files
- Quality checks to ensure AI-generated updates maintain accuracy

**Output**: `research/ai-update-prompts.md` (feeds into FR-007a, FR-007b, FR-007c)

---

### Research Deliverable Summary

**Phase 0 Output**: `specs/001-college-admissions-guide/research.md`

This file will consolidate:
- **Decisions Made**: Document generation approach (Markdown → Word → PDF/DOCX) - RESOLVED
- **Data Gathered**: Links to all 8 university requirement files, testing calendar, financial aid deadlines, career research, program mapping matrix, NC regulations, visit planning guide, AI update prompts
- **Sources Verified**: List of all authoritative sources consulted with access dates
- **Remaining Gaps**: Any information not available or requiring user input

**Estimated Research Time**: This research phase is substantial given the need to gather detailed information from 8+ authoritative sources per university, plus career research, testing calendars, and AI update prompt development. Plan for thorough fact-checking and citation of all sources.

---

## Phase 1: Content Design & Spreadsheet Structure

**Prerequisites**: Phase 0 research.md complete

### Phase 1 Deliverables

#### D1-001: Content Outline (`data-model.md`)

For a content project, the "data model" is the **content outline and information architecture**.

This file will document:

**1. Document Structure**
- Section hierarchy (matches content structure defined earlier)
- Content flow and reading order
- Cross-references between sections
- Page layout considerations (what content goes where)

**2. Content Entities** (from spec Key Entities section)
- Student Profile template (fields to track about Connor)
- University Profile template (structure for all 8 university sections)
- Career Path Guide template (structure for all 7 career sections)
- Timeline Entry template (structure for month-by-month items)
- Homeschool Documentation template (transcript format, validation tracking)
- AI Update Instructions template (FR-007a structure)

**3. Content Guidelines**
- Reading level target (≤ 10th grade Flesch-Kincaid)
- Citation format for sources
- Date format standards (MM/DD/YYYY per spec)
- Consistent terminology (glossary of admissions terms)

**4. Template Documents** (NEW - from clarification)
- Homeschool transcript template structure (FR-022a)
- Sample transcript content specifications (FR-022b)
- Transcript adaptability notes for all 8 universities (FR-022c)

**Output**: `specs/001-college-admissions-guide/data-model.md`

---

#### D1-002: Spreadsheet Structure (`contracts/`)

For a content project, "contracts" represent the **CSV file structure and spreadsheet tab templates**.

This directory will contain:

**1. Spreadsheet Tab Specifications**
- `README.md`: Overview of 16 CSV files and spreadsheet structure
- `university-tab-template.md`: Structure for each of 8 university CSV files
  - Columns: Task/Milestone, Date, Type (EA/ED/RD), Status, Notes, Responsible Party
  - Row categories: Testing, Application, Essays, Financial Aid, Decisions, Enrollment
- `career-tab-template.md`: Structure for each of 7 career interest CSV files
  - Columns: University, Program Name, Application Deadline, Program Requirements, Notes
  - Filters/sorting by deadline
- `master-timeline-template.md`: Structure for consolidated timeline CSV file
  - Columns: Date, University/Career, Category, Task, Status, Priority
  - Sorted chronologically from Feb 2026 - Aug 2027

**2. Data Validation Rules**
- Date formats and validation
- Status dropdown values (Not Started, In Progress, Completed, N/A)
- Priority levels (Critical, High, Medium, Low)

**3. Conditional Formatting** (to apply in Google Sheets after import)
- Overdue deadlines highlighted in red
- Upcoming deadlines (within 2 weeks) highlighted in yellow
- Completed items grayed out

**4. CSV Format Standards** (NEW - from clarification)
- UTF-8 encoding
- Comma delimiter
- Quote handling for fields with commas
- Header row structure
- Date format (MM/DD/YYYY for compatibility)

**Output**: `specs/001-college-admissions-guide/contracts/` directory with template specifications

---

#### D1-003: User Guide (`quickstart.md`)

For a content project, the "quickstart" is **instructions for using the deliverables**.

This file will document:

**1. How to Use the Guide Document**
- Navigation tips (using TOC, page numbers, cross-references)
- How to find university-specific information quickly
- How to find career-specific information quickly
- How to use the timeline section effectively
- How to verify information currency (check verification dates)

**2. How to Use the CSV Files and Google Sheets** (UPDATED - from clarification)
- **CSV to Google Sheets import process** (FR-002a):
  - Step-by-step instructions for importing 16 CSV files
  - Creating multi-tab workbook structure
  - Applying conditional formatting rules
  - Setting up formulas and data validation
- Overview of tab organization (university view vs career view vs master timeline)
- When to use each tab type
- How to track progress (updating status fields)
- How to add custom deadlines or notes
- How to filter and sort for specific information
- How to avoid accidental data loss (don't delete structure)

**3. AI-Assisted Monthly Updates** (NEW - from clarification)
- **How to use Claude/AI for monthly updates** (FR-007a):
  - Step-by-step guide for monthly verification
  - Which sources to check (8 universities, SAT/ACT, FAFSA)
  - How to provide URLs to AI
  - Example prompts for deadline checking
  - How to review AI-generated updates
  - How to regenerate PDF/DOCX after updates
  - How to re-import updated CSV files to Google Sheets

**4. Getting Started Checklist**
- Week 1: Read introduction and timeline overview
- Week 1: Review all 8 university profiles, mark top choices
- Week 1: Import CSV files to Google Sheets
- Week 2: Read homeschool requirements section thoroughly
- Week 2: Review transcript template and sample
- Week 3: Review career paths, narrow interests
- Week 4: Practice first AI-assisted update check
- Ongoing: Follow month-by-month timeline

**Output**: `specs/001-college-admissions-guide/quickstart.md`

---

### Phase 1 Quality Gates

Before proceeding to Phase 2 (task generation):

1. **Re-check Constitution Compliance**:
   - Verify content outline meets all 5 principles
   - Confirm step-by-step procedures planned for complex processes
   - Validate spreadsheet structure supports actionability
   - Verify AI update instructions are clear and actionable

2. **Completeness Check**:
   - All 8 universities have defined profile templates
   - All 7 careers have defined guide templates
   - All 16 CSV file structures are specified
   - User guide covers all deliverables including CSV import and AI updates
   - Transcript template specifications complete (template + sample)
   - AI update prompt templates complete

3. **Clarity Check**:
   - Content outline is clear enough to guide writing
   - CSV file templates have all required fields
   - Google Sheets import instructions are actionable
   - AI update instructions include specific prompts
   - User guide provides sufficient instructions

---

## Phase 2: Task Generation

**Note**: Phase 2 is executed by the `/speckit.tasks` command, NOT by `/speckit.plan`.

Phase 2 will generate `tasks.md` with dependency-ordered implementation tasks based on:
- Research tasks from Phase 0
- Content creation tasks from Phase 1 design
- CSV file creation tasks (16 files)
- Document assembly and formatting tasks (Markdown → Word → PDF/DOCX)
- AI update instructions and prompt template creation
- Transcript template creation (fillable + sample)
- Quality assurance and review tasks

This plan document ends after Phase 1 planning is complete.

---

## Next Steps

After this plan is approved:

1. **Execute Phase 0 Research** (can use Task tool with research agents):
   - RT-001: RESOLVED - Document generation approach clarified
   - RT-002 through RT-008: Execute research tasks
   - RT-009: Develop AI update prompt templates
   - Consolidate findings in research.md

2. **Execute Phase 1 Design**:
   - Create content outline (data-model.md) including transcript template specs
   - Create CSV file templates (contracts/) with import instructions
   - Create user guide (quickstart.md) including AI update procedures
   - Update agent context (if applicable)

3. **Run `/speckit.tasks`** to generate implementation task list

4. **Execute tasks** using `/speckit.implement` or manual implementation

---

**Clarifications Integrated** (Session 2026-02-13):
1. ✓ Document generation: Markdown → Word → PDF/DOCX
2. ✓ Spreadsheet format: CSV files with Google Sheets import instructions
3. ✓ Maintenance: AI-assisted monthly updates with specific prompts
4. ✓ Testing strategy: SAT primary with ACT backup
5. ✓ Transcript deliverables: Fillable template + anonymized sample

**Plan Status**: Updated with all clarifications resolved. Ready for Phase 0 execution.
