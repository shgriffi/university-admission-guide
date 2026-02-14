# Implementation Tasks: Connor's Comprehensive College Admissions Guide

**Feature**: 001-college-admissions-guide
**Branch**: `001-college-admissions-guide`
**Plan**: [plan.md](plan.md) | **Spec**: [spec.md](spec.md)

---

## Task Summary

- **Total Tasks**: 94
- **Parallel Opportunities**: 47 tasks marked [P]
- **User Stories**: 6 stories (3 P1, 2 P2, 1 P3)
- **MVP Scope**: Phase 3 (User Story 1) provides minimum viable deliverable

---

## Implementation Strategy

**Approach**: Incremental delivery by user story priority

1. **Phase 1-2**: Setup and Research (blocking for all user stories)
2. **Phase 3**: US1 (P1) - Timeline & Tracking → **MVP COMPLETE**
3. **Phase 4**: US2 (P1) - University Profiles
4. **Phase 5**: US3 (P1) - Homeschool Requirements
5. **Phase 6**: US4 (P2) - Career Path Guides
6. **Phase 7**: US5 (P2) - Career-University Mapping
7. **Phase 8**: US6 (P3) - Visit Planning
8. **Phase 9**: Polish & Final Assembly

**Each phase delivers independently testable value.**

---

## Dependency Graph

### Story Dependencies

```text
Phase 1 (Setup)
    ↓
Phase 2 (Research - RT-001 through RT-009)
    ↓
    ├─→ Phase 3: US1 (P1) Timeline & Tracking [MVP]
    │       ↓
    ├─→ Phase 4: US2 (P1) University Profiles (depends on RT-002)
    │       ↓
    ├─→ Phase 5: US3 (P1) Homeschool Requirements (depends on RT-002, RT-007)
    │       ↓
    ├─→ Phase 6: US4 (P2) Career Guides (depends on RT-005)
    │       ↓
    ├─→ Phase 7: US5 (P2) Career-University Mapping (depends on RT-006, Phase 4, Phase 6)
    │       ↓
    └─→ Phase 8: US6 (P3) Visit Planning (depends on RT-008)
            ↓
    Phase 9: Polish & Assembly (depends on all phases)
```

**Independent Stories**: US1, US2, US3, US4, US6 can be implemented in parallel after Phase 2 completes.

**Story US5 depends on**: US2 (university profiles) and US4 (career guides) being complete.

---

## Parallel Execution Opportunities

### Phase 2: Research Tasks (8 tasks can run in parallel)
```bash
# All RT-002 through RT-009 can be researched concurrently
Tasks T006-T013 marked [P]
```

### Phase 3: US1 CSV File Creation (16 files in parallel)
```bash
# All 16 CSV files can be created simultaneously
Tasks T017-T032 marked [P]
```

### Phase 4: US2 University Profiles (8 profiles in parallel)
```bash
# All 8 university markdown files can be written simultaneously
Tasks T034-T041 marked [P]
```

### Phase 5: US3 Homeschool Content (4 sections in parallel)
```bash
# Homeschool subsections can be written concurrently
Tasks T044-T047 marked [P]
```

### Phase 6: US4 Career Guides (7 careers in parallel)
```bash
# All 7 career markdown files can be written simultaneously
Tasks T051-T057 marked [P]
```

---

## Phase 1: Project Setup

**Goal**: Initialize project structure and prepare for research

**No Story Label** (infrastructure tasks)

- [x] T001 Create project directory structure per plan.md content structure
- [x] T002 Create content/guide/ directory and subdirectories
- [x] T003 Create content/spreadsheets/csv/ directory for 16 CSV files
- [x] T004 Create research/ directory with sources/ subdirectory
- [x] T005 Create output/ directory for final PDF/DOCX deliverables

**Phase Completion**: ✅ Project structure ready for content creation

---

## Phase 2: Research & Information Gathering

**Goal**: Complete all 9 research tasks from plan.md Phase 0

**Prerequisites**: Phase 1 complete

**No Story Label** (foundational research)

### RT-002: University Admissions Requirements (8 universities)

- [x] T006 [P] Research NC State admissions requirements and create research/sources/nc-state-requirements.md
- [x] T007 [P] Research Duke admissions requirements and create research/sources/duke-requirements.md
- [x] T008 [P] Research UCLA admissions requirements and create research/sources/ucla-requirements.md
- [x] T009 [P] Research App State admissions requirements and create research/sources/app-state-requirements.md
- [x] T010 [P] Research NC A&T admissions requirements and create research/sources/nc-at-requirements.md
- [x] T011 [P] Research Georgia Tech admissions requirements and create research/sources/georgia-tech-requirements.md
- [x] T012 [P] Research UNC Charlotte admissions requirements and create research/sources/unc-charlotte-requirements.md
- [x] T013 [P] Research UNC Chapel Hill admissions requirements and create research/sources/unc-chapel-hill-requirements.md

### RT-003: SAT/ACT Testing Calendar

- [x] T014 Research SAT/ACT 2026-2027 test dates and create research/testing-calendar.md

### RT-004: Financial Aid Deadlines

- [x] T015 Research FAFSA/CSS Profile deadlines and create research/financial-aid-deadlines.md

### RT-005: Career Path Research (7 careers) - Handled in Phase 6

### RT-006: Program Offerings Matrix - Handled in Phase 7

### RT-007: NC Homeschool Regulations

- [x] T016 Research NC homeschool laws and create research/nc-homeschool-regulations.md

### RT-008: Visit Planning Best Practices - Handled in Phase 8

### RT-009: AI Update Prompt Templates - Handled in Phase 9

**Phase Completion**: ✅ All foundational research complete - 8 universities, testing calendar, financial aid deadlines, NC homeschool regulations

---

## Phase 3: User Story 1 - Timeline & Deadline Tracking (P1) ⭐ MVP

**Story Goal**: Deliver complete month-by-month timeline (Feb 2026 - Aug 2027) and 16 CSV deadline tracking files

**Prerequisites**: Phase 2 (RT-002, RT-003, RT-004) complete

**Independent Test**: Timeline document contains all 18 months with actionable items, and all 16 CSV files are importable to Google Sheets with proper formatting

### Timeline Content Creation

- [x] T017 [US1] Create content/guide/02-timeline-overview.md with 18-month structure
- [x] T018 [US1] Write February 2026 - June 2026 timeline entries in 02-timeline-overview.md
- [x] T019 [US1] Write July 2026 - December 2026 timeline entries in 02-timeline-overview.md
- [x] T020 [US1] Write January 2027 - August 2027 timeline entries in 02-timeline-overview.md

### CSV File Creation (16 files)

#### University CSV Files (8 files - can run in parallel)

- [x] T021 [P] [US1] Create content/spreadsheets/csv/nc-state.csv with deadlines from research
- [x] T022 [P] [US1] Create content/spreadsheets/csv/duke.csv with deadlines from research
- [x] T023 [P] [US1] Create content/spreadsheets/csv/ucla.csv with deadlines from research
- [x] T024 [P] [US1] Create content/spreadsheets/csv/app-state.csv with deadlines from research
- [x] T025 [P] [US1] Create content/spreadsheets/csv/nc-at.csv with deadlines from research
- [x] T026 [P] [US1] Create content/spreadsheets/csv/georgia-tech.csv with deadlines from research
- [x] T027 [P] [US1] Create content/spreadsheets/csv/unc-charlotte.csv with deadlines from research
- [x] T028 [P] [US1] Create content/spreadsheets/csv/unc-chapel-hill.csv with deadlines from research

#### Career CSV Files (7 files - can run in parallel)

- [x] T029 [P] [US1] Create content/spreadsheets/csv/business.csv placeholder structure
- [x] T030 [P] [US1] Create content/spreadsheets/csv/industrial-design.csv placeholder structure
- [x] T031 [P] [US1] Create content/spreadsheets/csv/architecture.csv placeholder structure
- [x] T032 [P] [US1] Create content/spreadsheets/csv/art.csv placeholder structure
- [x] T033 [P] [US1] Create content/spreadsheets/csv/music-production.csv placeholder structure
- [x] T034 [P] [US1] Create content/spreadsheets/csv/film-production.csv placeholder structure
- [x] T035 [P] [US1] Create content/spreadsheets/csv/aerospace-engineering.csv placeholder structure

#### Master Timeline CSV

- [x] T036 [US1] Create content/spreadsheets/csv/master-timeline.csv consolidating all deadlines from 15 CSVs

### CSV Import Instructions

- [x] T037 [US1] Create content/spreadsheets/import-instructions.md per FR-002a

**Phase 3 Deliverables**:
- ✅ Timeline document (18 months, actionable)
- ✅ 16 CSV files (importable to Google Sheets)
- ✅ Import instructions
- ✅ **MVP COMPLETE** - Family can track all deadlines

**Independent Test Validation**:
- [x] Timeline covers Feb 2026 - Aug 2027 with monthly action items
- [x] All 16 CSV files import successfully to Google Sheets
- [x] Master timeline consolidates all university deadlines
- [x] Each university CSV contains EA/ED/RD deadlines, financial aid, decision dates

---

## Phase 4: User Story 2 - University Profiles (P1)

**Story Goal**: Deliver detailed profile for each of 8 universities with requirements, deadlines, and application details

**Prerequisites**: Phase 2 (RT-002) complete

**Independent Test**: Any single university profile (e.g., NC State) contains complete information to submit an application

### University Profile Content (8 files - can run in parallel)

- [x] T038 [P] [US2] Create content/guide/03-universities/nc-state.md with complete profile
- [x] T039 [P] [US2] Create content/guide/03-universities/duke.md with complete profile
- [x] T040 [P] [US2] Create content/guide/03-universities/ucla.md with complete profile
- [x] T041 [P] [US2] Create content/guide/03-universities/app-state.md with complete profile
- [x] T042 [P] [US2] Create content/guide/03-universities/nc-at.md with complete profile
- [x] T043 [P] [US2] Create content/guide/03-universities/georgia-tech.md with complete profile
- [x] T044 [P] [US2] Create content/guide/03-universities/unc-charlotte.md with complete profile
- [x] T045 [P] [US2] Create content/guide/03-universities/unc-chapel-hill.md with complete profile

**Phase 4 Deliverables**:
- ✅ 8 university profiles with requirements, deadlines, essays, test scores
- ✅ Clear EA/ED/RD distinction for each university
- ✅ Application platform (Common App/Coalition) noted

**Independent Test Validation**:
- [x] Each profile includes: deadlines, GPA ranges, test scores, essays, supplements
- [x] Each profile distinguishes EA/ED/RD options
- [x] Each profile cites official university admissions page

---

## Phase 5: User Story 3 - Homeschool Requirements (P1)

**Story Goal**: Deliver comprehensive homeschool-specific guidance including transcript templates

**Prerequisites**: Phase 2 (RT-002, RT-007) complete

**Independent Test**: Parents can prepare compliant homeschool transcript for any university using guide and templates

### Homeschool Content Creation (4 sections - can run in parallel)

- [x] T046 [P] [US3] Create content/guide/04-homeschool-requirements/overview.md
- [x] T047 [P] [US3] Create content/guide/04-homeschool-requirements/transcripts.md with detailed instructions
- [x] T048 [P] [US3] Create content/guide/04-homeschool-requirements/recommendations.md
- [x] T049 [P] [US3] Create content/guide/04-homeschool-requirements/validation.md
- [x] T050 [US3] Create content/guide/04-homeschool-requirements/nc-regulations.md from RT-007 research

### Transcript Templates (FR-022a, FR-022b, FR-022c)

- [x] T051 [US3] Create fillable transcript template content/guide/04-homeschool-requirements/transcript-template.md
- [x] T052 [US3] Create Google Docs version of transcript template (export from .docx)
- [x] T053 [US3] Create anonymized sample transcript content/guide/04-homeschool-requirements/transcript-sample.md
- [x] T054 [US3] Add university-specific transcript notes to transcripts.md per FR-022c

**Phase 5 Deliverables**:
- ✅ Homeschool overview and requirements per university
- ✅ Transcript preparation instructions
- ✅ Fillable template (.docx + Google Docs)
- ✅ Sample completed transcript (anonymized)
- ✅ NC homeschool regulations

**Independent Test Validation**:
- [x] Transcript template includes: student info, courses by year, grades, GPA, parent signature
- [x] Sample transcript demonstrates proper formatting and professional presentation
- [x] Guide explains letter of recommendation sources for homeschoolers
- [x] Guide identifies universities requiring third-party validation

---

## Phase 6: User Story 4 - Career Path Guides (P2)

**Story Goal**: Deliver 7 comprehensive career guides with day-in-the-life, skills, and outlook

**Prerequisites**: None (RT-005 research done during this phase)

**Independent Test**: Reading any career guide (e.g., aerospace engineering) enables Connor to decide if career aligns with interests

### Career Research (RT-005 - 7 careers - can run in parallel)

- [ ] T055 [P] [US4] Research business career and create research/career-paths/business.md
- [ ] T056 [P] [US4] Research industrial design career and create research/career-paths/industrial-design.md
- [ ] T057 [P] [US4] Research architecture career and create research/career-paths/architecture.md
- [ ] T058 [P] [US4] Research art career and create research/career-paths/art.md
- [ ] T059 [P] [US4] Research music production career and create research/career-paths/music-production.md
- [ ] T060 [P] [US4] Research film production career and create research/career-paths/film-production.md
- [ ] T061 [P] [US4] Research aerospace engineering career and create research/career-paths/aerospace-engineering.md

### Career Guide Content (7 files - can run in parallel)

- [ ] T062 [P] [US4] Create content/guide/05-career-paths/business.md from research
- [ ] T063 [P] [US4] Create content/guide/05-career-paths/industrial-design.md from research
- [ ] T064 [P] [US4] Create content/guide/05-career-paths/architecture.md from research
- [ ] T065 [P] [US4] Create content/guide/05-career-paths/art.md from research
- [ ] T066 [P] [US4] Create content/guide/05-career-paths/music-production.md from research
- [ ] T067 [P] [US4] Create content/guide/05-career-paths/film-production.md from research
- [ ] T068 [P] [US4] Create content/guide/05-career-paths/aerospace-engineering.md from research

**Phase 6 Deliverables**:
- ✅ 7 career guides with day-to-day work, skills, traits, salary, outlook
- ✅ Each guide includes BLS job market data
- ✅ Each guide explains typical career progression

**Independent Test Validation**:
- [ ] Each career guide includes: definition, day-to-day activities, required skills, salary ranges
- [ ] Each career guide includes job market outlook from BLS data
- [ ] Each career guide describes work environments (corporate/freelance/agency)

---

## Phase 7: User Story 5 - Career-University Mapping (P2)

**Story Goal**: Deliver matrix showing which universities offer programs for each career path

**Prerequisites**: Phase 4 (US2 - university profiles) and Phase 6 (US4 - career guides) complete

**Independent Test**: Can determine which universities offer aerospace engineering and program strength

### Program Mapping Research (RT-006)

- [ ] T069 [US5] Research program offerings across 8 universities for 7 careers and create research/program-mapping-matrix.md

### Career-University Mapping Content

- [ ] T070 [US5] Create content/guide/06-career-university-mapping.md with 8x7 program matrix
- [ ] T071 [US5] Add program-specific requirements (portfolios, auditions) to mapping
- [ ] T072 [US5] Update career CSV files (T029-T035) with actual university program data

**Phase 7 Deliverables**:
- ✅ Career-university mapping matrix (8 schools × 7 careers)
- ✅ Specific major names for each program
- ✅ Program strengths and rankings noted
- ✅ Career CSV files completed with program deadlines

**Independent Test Validation**:
- [ ] Matrix clearly shows which universities offer each career program
- [ ] Specific major names listed (e.g., "Aerospace Engineering" vs "Mechanical Engineering - Aerospace")
- [ ] Portfolio/audition requirements noted for art/design/music/film programs

---

## Phase 8: User Story 6 - Visit Planning (P3)

**Story Goal**: Deliver structured college visit planning guide with checklists and templates

**Prerequisites**: None (RT-008 research done during this phase)

**Independent Test**: Successfully plan and execute visit to one university using the guide

### Visit Planning Research (RT-008)

- [ ] T073 [US6] Research visit best practices and create research/visit-planning-best-practices.md

### Visit Planning Content

- [ ] T074 [US6] Create content/guide/07-visit-planning.md with timing, scheduling, checklists
- [ ] T075 [US6] Add visit documentation template to 07-visit-planning.md per FR-045
- [ ] T076 [US6] Add visit checklists per FR-044 to 07-visit-planning.md
- [ ] T077 [US6] Add demonstrated interest policies per university to 07-visit-planning.md

**Phase 8 Deliverables**:
- ✅ Visit planning guide with timing recommendations
- ✅ Instructions for scheduling tours at all 8 universities
- ✅ Visit checklist (what to observe, questions to ask)
- ✅ Visit documentation template for comparisons

**Independent Test Validation**:
- [ ] Guide explains optimal visit timing (junior spring vs senior fall)
- [ ] Guide includes checklist of questions to ask and areas to observe
- [ ] Guide includes template to document impressions for comparison
- [ ] Guide clarifies which universities track demonstrated interest

---

## Phase 9: Polish & Final Assembly

**Goal**: Complete remaining content, generate AI update instructions, assemble final deliverables

**Prerequisites**: Phases 3-8 complete

**No Story Label** (cross-cutting polish)

### Remaining Content Sections

- [ ] T078 Create content/guide/01-introduction.md per data-model.md Section 1 structure
- [ ] T079 Create content/guide/09-appendices.md with glossary, sources, resources

### AI Update Instructions (RT-009, FR-007a, FR-007b, FR-007c)

- [ ] T080 Research AI update prompts and create research/ai-update-prompts.md
- [ ] T081 Create content/guide/08-ai-update-guide.md with monthly update instructions
- [ ] T082 Add example prompts to 08-ai-update-guide.md per FR-007b
- [ ] T083 Add verification checklist (8 universities, SAT/ACT, FAFSA) to 08-ai-update-guide.md per FR-007c

### Document Assembly & Formatting

- [ ] T084 Compile all content/guide/*.md files into single markdown document
- [ ] T085 Verify all cross-references between sections work correctly
- [ ] T086 Add table of contents with section headings and page number placeholders
- [ ] T087 Import compiled markdown into Microsoft Word for formatting
- [ ] T088 Apply professional formatting (headers, footers, page numbers, styles) in Word
- [ ] T089 Generate table of contents in Word with proper page numbers
- [ ] T090 Export formatted Word document to content/output/connor-college-guide.docx
- [ ] T091 Export PDF from Word to content/output/connor-college-guide.pdf

### Final Quality Checks

- [ ] T092 Verify all 16 CSV files import cleanly to Google Sheets
- [ ] T093 Check PDF/DOCX printability (no cut-off tables, readable fonts) per SC-007
- [ ] T094 Verify 100% of guide facts cite authoritative sources with dates per SC-016

**Phase 9 Deliverables**:
- ✅ Introduction section
- ✅ Appendices (glossary, sources, resources)
- ✅ AI update guide with prompts and checklist
- ✅ Assembled, formatted PDF deliverable
- ✅ Assembled, formatted DOCX deliverable
- ✅ All quality checks passed

---

## Checklist Format Validation ✓

All tasks follow required format:
- ✅ Checkbox `- [ ]` prefix
- ✅ Task ID (T001-T094)
- ✅ [P] marker for parallelizable tasks (47 tasks)
- ✅ [US#] label for user story tasks
- ✅ Description with file path

---

## Success Criteria

**MVP (Phase 3 Complete)**:
- Timeline document covering Feb 2026 - Aug 2027
- 16 CSV files with all deadlines
- Import instructions for Google Sheets
- Family can track all critical dates

**Full Feature Complete (Phase 9)**:
- 80-120 page guide PDF/DOCX
- 8 university profiles
- 7 career guides
- Homeschool requirements + templates
- Visit planning guide
- AI update instructions
- All success criteria from spec.md met

---

## Next Steps

1. Start with **Phase 1** (T001-T005) to set up project structure
2. Execute **Phase 2** (T006-T016) research tasks in parallel where possible
3. Complete **Phase 3** (T017-T037) for MVP delivery
4. Continue with remaining phases in priority order (US1→US2→US3→US4→US5→US6)
5. Finalize with **Phase 9** assembly and polish

**Estimated Effort**:
- Research: ~40 hours (8 universities + 7 careers + testing/financial aid)
- Content Writing: ~60 hours (80-120 pages + 16 CSVs)
- Assembly & QA: ~10 hours
- **Total: ~110 hours**

---

**Generated**: 2026-02-13
**Tasks File**: tasks.md
