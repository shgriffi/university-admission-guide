# Feature Specification: Connor's Comprehensive College Admissions Guide

**Feature Branch**: `001-college-admissions-guide`
**Created**: 2026-02-13
**Status**: Draft
**Input**: User description: "I am building a comprehensive guide for college admissions for my son Connor Griffin. He is 17 and is currently in 11th grade with more more year to go. This guide needs to cover admissions requirements, deadlines, pre-requisites and any additional information we as parents need to know to ensure he completes what has to be done. He is interested in many areas and also several colleges, therefore the guide needs to be broken down by his interests, and what universities and requirements he should follow per each interest if he were to seek that. Additionally, it should have information about setting up visits and a timeline for that. THis needs to be a comprehensive timeline that we can follow, including when he should finalize any standardized tests such as the SAT. He is interested in attending North Carolina State University, Duke University, UCLA as his primary choices with Appalachian State University, North Carolina A&T University, Georgia Tech, University of North Carolina at Charlotte and University of North Carolina at Chapel Hill as his backups. He is currently exploring potential career paths in business, industrial design, architecture, art, music production, film production, aerospace engineering. This needs to also include career guides that are informative about what each career path is, and what a day in the life of each of those careers would look like, as well as common traits and skills to be successful in those careers."

**CRITICAL CONTEXT**: Connor is homeschooled and has been his entire life. He does not have a traditional high school GPA from an accredited institution - his GPA is parent-calculated. He takes standardized tests annually to track academic progress. This significantly impacts transcript requirements, GPA documentation, letters of recommendation, course validation, and university-specific homeschool applicant requirements.

## Clarifications

### Session 2026-02-13

- Q: What tool/process should be used to convert the markdown content into the final formatted PDF/DOCX deliverable with table of contents, page numbers, and professional layout? → A: Markdown files maintained as source, manually formatted in Microsoft Word, exported to PDF/DOCX
- Q: Should the deadline tracking spreadsheet be delivered in Microsoft Excel format (.xlsx) or Google Sheets format for the family to use? → A: Store spreadsheet data as CSV files locally with the project for version control, with instructions for manual import to Google Sheets for family use
- Q: Who is responsible for maintaining and updating the guide when university deadlines or requirements change after initial delivery? → A: Guide includes thorough instructions for using Claude or AI to update the guide with the latest information on a monthly basis
- Q: Will Connor take both the SAT and ACT, or focus primarily on one test? This affects which testing calendars to emphasize and timeline planning. → A: Focus primarily on SAT with ACT as backup option
- Q: Should the guide include a fillable template for Connor's homeschool transcript, or only provide instructions on how to create one? → A: Include both detailed instructions AND a fillable Word/Google Docs template, plus a sample completed transcript (anonymized) as an example

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Comprehensive Timeline and Deadline Tracking (Priority: P1)

As parents and Connor, we need a complete month-by-month timeline from now (February 2026, junior year) through college enrollment (August 2027) that tells us exactly what actions to take each month, including SAT test dates, application deadlines, financial aid deadlines, and decision dates for all eight universities.

**Why this priority**: Missing a single critical deadline can eliminate a college option entirely. This is the most time-sensitive and consequential aspect of the admissions process. Without a clear timeline, families risk missing opportunities that cannot be recovered.

**Independent Test**: Can be fully tested by reviewing the timeline from February 2026 through August 2027 and verifying that all critical dates are present and actionable, and that following the timeline results in meeting all deadlines for at least one university application.

**Acceptance Scenarios**:

1. **Given** we are in February 2026 (junior year), **When** we view the timeline, **Then** we see specific actions for each month including: SAT registration dates, SAT test dates, college visit windows, application opening dates, and financial aid preparation steps
2. **Given** we are approaching an SAT test date, **When** we check the timeline, **Then** we see the registration deadline, test date, score release date, and whether this is the final opportunity to test before early action/early decision deadlines
3. **Given** we want to apply early decision to Duke, **When** we review the timeline, **Then** we see all early decision requirements, deadlines, and dependencies (e.g., must complete SAT by October 2026)
4. **Given** we are in senior year fall 2026, **When** we view November deadlines, **Then** we see all early action/early decision deadlines for the eight target schools with specific dates and requirements
5. **Given** we completed an application, **When** we check the timeline, **Then** we see when to expect admission decisions and when financial aid packages will be available
6. **Given** we receive the deadline tracking spreadsheet, **When** we open it, **Then** we see separate tabs for each university (8 tabs), each career interest (7 tabs), and a master timeline (1 tab), with each tab containing all relevant deadlines in a trackable format with date, status, and notes columns
7. **Given** we want to track Duke-specific deadlines, **When** we navigate to the Duke university tab in the spreadsheet, **Then** we see all Duke deadlines (application, financial aid, decision dates, visit opportunities) organized chronologically with checkboxes or status indicators
8. **Given** Connor is researching aerospace engineering deadlines, **When** we navigate to the aerospace engineering career tab in the spreadsheet, **Then** we see deadlines for all universities offering aerospace programs (Georgia Tech, NC State, UCLA) with program-specific requirements noted

---

### User Story 2 - University-Specific Requirements and Deadlines (Priority: P1)

As parents and Connor, we need detailed profiles for each of the eight target universities (NC State, Duke, UCLA, App State, NC A&T, Georgia Tech, UNC Charlotte, UNC Chapel Hill) that clearly state their admissions requirements, application deadlines (early and regular), required test scores, GPA expectations, required essays, supplemental materials, and financial aid deadlines.

**Why this priority**: Each university has unique requirements and deadlines. Without complete, accurate information for each school, Connor could submit incomplete applications or miss school-specific requirements, resulting in automatic rejection.

**Independent Test**: Can be fully tested by reviewing the requirements for any one university (e.g., NC State) and verifying that all necessary information to complete an application is present, accurate, and actionable.

**Acceptance Scenarios**:

1. **Given** we are researching NC State, **When** we view its profile, **Then** we see: application deadline dates (early action and regular decision), required GPA range, required/optional SAT scores, number and topics of required essays, supplemental materials needed, and financial aid deadlines
2. **Given** we are comparing Duke and UCLA requirements, **When** we review both profiles, **Then** we can clearly identify differences in their requirements (e.g., different essay prompts, different test score expectations, different supplemental material requirements)
3. **Given** Connor is interested in aerospace engineering, **When** we view Georgia Tech's profile, **Then** we see specific requirements for the aerospace engineering program in addition to general admissions requirements
4. **Given** we need to plan application timing, **When** we review all eight university profiles, **Then** we can identify which schools offer early action, early decision, or only regular decision, and their respective deadlines
5. **Given** we are preparing applications, **When** we check UNC Chapel Hill's requirements, **Then** we see clear indication of NC resident vs. out-of-state requirements and any special considerations

---

### User Story 3 - Homeschool-Specific Application Requirements (Priority: P1)

As homeschooling parents and Connor, we need to understand the specific additional requirements, documentation, and processes that apply to homeschool applicants at each of the eight universities, including how to prepare transcripts, validate coursework, document GPA, obtain appropriate letters of recommendation, and meet any additional testing or portfolio requirements that homeschooled students must fulfill.

**Why this priority**: Homeschool applicants face unique challenges that traditional students do not. Each university has different policies for homeschoolers - some require additional SAT Subject Tests, detailed course descriptions, portfolios of work, third-party validation, or specific transcript formats. Failing to meet homeschool-specific requirements will result in automatic rejection regardless of Connor's qualifications. This is P1 because without this information, applications will be incomplete.

**Independent Test**: Can be fully tested by reviewing the homeschool requirements for any one university (e.g., Duke) and verifying that all necessary homeschool-specific documentation and requirements are clearly explained and actionable.

**Acceptance Scenarios**:

1. **Given** we are preparing Connor's transcript for NC State, **When** we review the homeschool requirements, **Then** we see: required transcript format, how to calculate and document GPA, whether course descriptions are required, if coursework needs third-party validation, and NC-specific homeschool regulations that apply
2. **Given** we need letters of recommendation for Duke, **When** we check the homeschool guide, **Then** we see who can provide recommendations for homeschoolers (outside instructors, tutors, coaches, community leaders vs. parents), how many are required, and any special considerations
3. **Given** Connor has taken annual standardized tests for academic tracking, **When** we review testing requirements, **Then** we see whether these tests can supplement his application, whether SAT Subject Tests are required or recommended for homeschoolers, and which test scores universities want to see
4. **Given** we are preparing application materials, **When** we check UCLA's homeschool requirements, **Then** we see California-specific homeschool documentation needed, whether UCLA requires course syllabi or reading lists, and if Connor needs to validate his homeschool status through specific California channels
5. **Given** Connor's curriculum includes parent-taught courses, **When** we review the homeschool guide, **Then** we see which universities require outside validation (community college courses, AP exams, third-party curriculum, online accredited courses) and how to document self-designed curriculum
6. **Given** we are determining which universities to apply to, **When** we review homeschool policies, **Then** we can identify which of the eight universities are most homeschool-friendly vs. which have more restrictive policies that may disadvantage homeschool applicants

---

### User Story 4 - Career Path Exploration and Information (Priority: P2)

As Connor, I need comprehensive career guides for each of the seven career paths I'm exploring (business, industrial design, architecture, art, music production, film production, aerospace engineering) that explain what each career is, what a typical day looks like, what skills and traits are needed for success, typical career progression, and salary expectations.

**Why this priority**: Understanding career realities helps Connor make informed decisions about which majors to pursue and which universities align best with his interests. This prevents costly major changes or career dissatisfaction later. However, it's P2 because college applications can proceed without finalizing career choice.

**Independent Test**: Can be fully tested by reading any one career guide (e.g., aerospace engineering) and determining whether Connor can understand the career well enough to decide if it aligns with his interests and strengths.

**Acceptance Scenarios**:

1. **Given** Connor is curious about aerospace engineering, **When** he reads the aerospace engineering career guide, **Then** he sees: a clear definition of the career, what aerospace engineers actually do day-to-day, required skills (math, physics, problem-solving), personality traits that succeed (detail-oriented, analytical), typical career path (entry-level to senior roles), and realistic salary ranges
2. **Given** Connor is comparing music production and film production, **When** he reviews both career guides, **Then** he can identify similarities (creative, project-based) and differences (technical focus, work environment, job market)
3. **Given** Connor wants to understand the business career path, **When** he reads the business guide, **Then** he sees that "business" encompasses multiple specializations (finance, marketing, management) with different day-to-day work and required skills
4. **Given** Connor is evaluating whether he has the right traits for architecture, **When** he reviews the architecture career guide, **Then** he can compare his current skills and interests against the listed requirements and identify gaps or alignments
5. **Given** Connor is concerned about career stability, **When** he reads any career guide, **Then** he sees job market outlook, demand trends, and typical employment settings (corporate, freelance, agency, etc.)

---

### User Story 5 - Career-to-University Program Mapping (Priority: P2)

As parents and Connor, we need to understand which of the eight target universities offer strong programs for each of Connor's seven career interests, including specific major names, program rankings or reputation, unique program features, and admission selectivity for those specific programs.

**Why this priority**: Some universities excel in certain programs but not others. Knowing which schools align best with which career paths helps prioritize applications and increases admission chances by targeting the right programs. It's P2 because initial applications don't require declaring a major at most schools.

**Independent Test**: Can be fully tested by selecting one career path (e.g., industrial design) and one university (e.g., NC State) and verifying whether the guide clearly indicates if that program is available, how strong it is, and what major to apply under.

**Acceptance Scenarios**:

1. **Given** Connor is interested in aerospace engineering, **When** we review the career-to-university mapping, **Then** we see that Georgia Tech, NC State, and UCLA have aerospace engineering programs, with notes on program strengths, while Duke, UNC Chapel Hill, App State, NC A&T, and UNC Charlotte either don't offer it or offer related alternatives
2. **Given** Connor wants to study industrial design, **When** we check the mapping, **Then** we see which universities offer industrial design, product design, or related programs, and whether they're in the engineering, art, or design schools
3. **Given** Connor is comparing film production programs, **When** we review UCLA vs. other schools, **Then** we see UCLA's film school reputation and specific program details compared to film/media programs at other target schools
4. **Given** we need to understand competitiveness, **When** we review architecture programs, **Then** we see that some architecture programs (like at UNC Charlotte) may have additional portfolio requirements or separate admission processes
5. **Given** Connor is undecided between careers, **When** we review the mapping, **Then** we can identify which universities offer the most flexibility and strongest programs across multiple career interests (e.g., which schools are strong in both business and engineering)

---

### User Story 6 - College Visit Planning and Scheduling (Priority: P3)

As parents and Connor, we need a structured guide for planning college visits including when to visit (optimal timing in the admissions timeline), how to schedule visits, what to do during visits (tours, information sessions, class observations, overnight stays), questions to ask, and how to document visit impressions for later comparison.

**Why this priority**: College visits provide valuable insight into campus culture, programs, and fit, influencing both application decisions and final college choice. However, it's P3 because visits can occur after applications are submitted and are not strictly required for admission to most schools.

**Independent Test**: Can be fully tested by using the visit planning guide to successfully plan and execute a visit to one university, resulting in documented impressions and information that aids decision-making.

**Acceptance Scenarios**:

1. **Given** we want to visit Duke, **When** we use the visit planning guide, **Then** we see optimal timing (e.g., junior year spring or senior year fall, avoid exam periods), how to register for official tours, and whether overnight stays or class visits are available
2. **Given** we are planning multiple visits, **When** we review the guide, **Then** we see a suggested sequence (e.g., visit safety schools first to practice, visit top choices when we're better prepared) and how to efficiently schedule visits to nearby schools in the same trip
3. **Given** we are on a Duke campus tour, **When** we reference the visit guide, **Then** we have a checklist of questions to ask (about specific programs, campus resources, student life, financial aid) and areas to observe (facilities, student interactions, campus safety)
4. **Given** we completed visits to three universities, **When** we use the documentation template, **Then** we can record comparable information (impressions, pros/cons, program fit, campus culture) for each school to support later decision-making
5. **Given** we cannot afford to visit all eight schools, **When** we review the visit guide, **Then** we see guidance on prioritizing visits (top choices first, virtual tour alternatives, admitted student days for final decisions) and whether visits influence admission chances

---

### Edge Cases

- What happens when application deadlines change after the guide is created (e.g., university updates their deadline)?
- How does the timeline accommodate if Connor takes the SAT multiple times and doesn't achieve desired scores until late in the application cycle?
- What if Connor's career interests change significantly during senior year, requiring different university program considerations?
- How does the guide handle universities that don't offer one of Connor's career interests at all?
- What happens if Connor gets deferred or waitlisted rather than accepted/rejected?
- How does the guide account for early decision binding commitments vs. early action non-binding options?
- What if financial aid packages make top-choice schools unaffordable compared to backup schools?
- How does the guide handle gap year considerations if Connor decides not to enroll immediately after high school?
- What if a university changes its homeschool policy mid-application cycle (e.g., suddenly requires SAT Subject Tests)?
- How does the guide address if Connor's parent-calculated GPA differs significantly from standardized test performance?
- What if some universities reject Connor's homeschool transcript format and require third-party accreditation that takes months to obtain?
- How does the guide handle if Connor needs to take community college courses to validate homeschool coursework but enrollment deadlines conflict with application timelines?

## Requirements *(mandatory)*

### Functional Requirements

#### Output Deliverables

- **FR-001**: The complete guide MUST be deliverable as a formatted document or PDF that can be read, printed, and shared digitally
- **FR-002**: Spreadsheet data MUST be provided as CSV (comma-separated values) files for tracking and managing key dates and deadlines, with one CSV file per tab (16 total CSV files)
- **FR-002a**: Clear instructions MUST be provided for importing the CSV files into Google Sheets, including how to create a new Google Sheets workbook with multiple tabs from the CSV files and how to apply formatting, formulas, and conditional formatting rules
- **FR-003**: The spreadsheet structure MUST include separate tabs (CSV files) organized by university (one tab per target university: NC State, Duke, UCLA, App State, NC A&T, Georgia Tech, UNC Charlotte, UNC Chapel Hill)
- **FR-004**: The spreadsheet MUST include separate tabs organized by career interest (one tab per career path: business, industrial design, architecture, art, music production, film production, aerospace engineering)
- **FR-005**: The spreadsheet MUST include a master timeline tab showing all critical dates in chronological order from February 2026 through August 2027
- **FR-006**: Each spreadsheet tab MUST support date tracking with columns for: task/milestone name, target date, completion status, notes, and responsible party
- **FR-007**: The document/PDF MUST be structured with a table of contents, clear section headings, and page numbers for easy navigation
- **FR-007a**: The guide MUST include a dedicated "Keeping This Guide Updated" section with thorough step-by-step instructions for using Claude or other AI assistants to update the guide with the latest information from official university sources on a monthly basis
- **FR-007b**: AI update instructions MUST include specific prompts or templates the family can use with Claude/AI to fetch current deadlines from official university websites, identify what has changed, and generate updated markdown files and CSV files
- **FR-007c**: Update instructions MUST include a monthly verification checklist listing all critical sources to check (all 8 university admissions pages, SAT/ACT test calendars, FAFSA dates) and how to provide these URLs to the AI for automated checking

#### Timeline and Deadline Management (User Story 1)

- **FR-008**: Guide MUST provide a month-by-month timeline from February 2026 through August 2027 with specific action items for each month
- **FR-009**: Guide MUST include all SAT test dates for 2026-2027, registration deadlines, and score release dates with clear indication of which test dates are final opportunities for early vs. regular decision applications, with SAT emphasized as the primary test
- **FR-009a**: Guide MUST include ACT test dates and registration information as a backup testing option, with guidance on when to consider switching to ACT if SAT scores are not competitive
- **FR-010**: Guide MUST list application deadlines for all eight target universities, distinguishing between early action, early decision, and regular decision deadlines
- **FR-011**: Guide MUST include financial aid deadlines for each university, including FAFSA, CSS Profile, and school-specific financial aid forms
- **FR-012**: Guide MUST indicate decision notification dates for each application type (early action, early decision, regular decision) for all eight universities
- **FR-013**: Timeline MUST flag critical path dependencies (e.g., "SAT must be completed by October 2026 for early decision applications") and emphasize SAT test dates in the primary timeline with ACT dates noted as alternatives
- **FR-013a**: Timeline MUST include decision points for evaluating SAT performance and determining whether to continue with SAT or switch to ACT preparation
- **FR-014**: Guide MUST include college application system opening dates (Common App, Coalition App, university-specific portals)

#### University Profiles (User Story 2)

- **FR-015**: Guide MUST provide a detailed profile for each of the eight target universities: NC State, Duke, UCLA, App State, NC A&T, Georgia Tech, UNC Charlotte, UNC Chapel Hill
- **FR-016**: Each university profile MUST include: application deadline dates (with specific dates in MM/DD/YYYY format), required and optional standardized test scores, GPA expectations or middle 50% ranges, essay requirements with prompts or topics, supplemental materials needed, and contact information
- **FR-017**: University profiles MUST clearly distinguish between early action (non-binding), early decision (binding), and regular decision options where available
- **FR-018**: Guide MUST indicate which universities are in-state (NC) vs. out-of-state for tuition and admissions consideration purposes
- **FR-019**: University profiles MUST include links or references to authoritative sources (official university admissions pages) for verification
- **FR-020**: Each profile MUST note the application platform used (Common App, Coalition App, university-specific system)

#### Homeschool Requirements (User Story 3)

- **FR-021**: Guide MUST document homeschool-specific admission requirements for each of the eight universities, including any additional documentation, testing, or validation required beyond what traditional applicants submit
- **FR-022**: Guide MUST provide detailed instructions for preparing homeschool transcripts that meet each university's requirements, including required format, GPA calculation methods, course descriptions, grading scales, and whether parent signatures are acceptable
- **FR-022a**: Guide MUST include a fillable homeschool transcript template in both Word (.docx) and Google Docs formats that parents can customize with Connor's information, including sections for student information, courses by year, grades, GPA calculation, and parent signature
- **FR-022b**: Guide MUST include a sample completed homeschool transcript (with anonymized/fictional student data) that demonstrates proper formatting, appropriate course descriptions, GPA calculation, and professional presentation that meets university standards
- **FR-022c**: Transcript template MUST be adaptable to all 8 target universities' requirements, with notes indicating which sections or formats are preferred by specific universities
- **FR-023**: Guide MUST identify which universities require or recommend SAT Subject Tests specifically for homeschool applicants and which subject areas align with Connor's intended majors
- **FR-024**: Guide MUST explain acceptable sources for letters of recommendation for homeschool students at each university (e.g., outside instructors, tutors, coaches, employers, community leaders) and whether parent recommendations are permitted
- **FR-025**: Guide MUST document whether each university requires third-party validation of homeschool coursework (AP exams, community college dual enrollment, accredited online courses, CLEP exams) and how to obtain such validation
- **FR-026**: Guide MUST indicate which universities are most homeschool-friendly based on policies, acceptance rates for homeschoolers, and institutional support for homeschool applicants
- **FR-027**: Guide MUST include North Carolina-specific homeschool regulations and documentation (homeschool registration, required testing, notification requirements) that may be requested by universities
- **FR-028**: Guide MUST address how Connor's annual standardized testing history can supplement his application and which universities will consider these scores
- **FR-029**: Timeline MUST include homeschool-specific tasks: finalizing transcript format (by summer before senior year), obtaining outside letters of recommendation (by fall senior year), completing any required third-party coursework validation, and preparing detailed course descriptions or syllabi if required

#### Career Path Information (User Story 4)

- **FR-030**: Guide MUST provide comprehensive career guides for all seven career paths: business, industrial design, architecture, art, music production, film production, aerospace engineering
- **FR-031**: Each career guide MUST include: clear definition of the career field, description of typical day-to-day work activities, required technical skills, required soft skills and personality traits, typical career progression path, and realistic salary ranges (entry-level and experienced)
- **FR-032**: Career guides MUST explain educational requirements (degree level, relevant majors, certifications)
- **FR-033**: Each career guide MUST provide job market outlook and demand trends
- **FR-034**: Career guides MUST describe typical work environments and employment settings (corporate, freelance, agency, academic, etc.)
- **FR-035**: Guide MUST use accessible language appropriate for a high school junior (11th grade reading level or below)

#### Career-University Mapping (User Story 5)

- **FR-036**: Guide MUST map each of the seven career paths to relevant programs at each of the eight universities, indicating which schools offer programs aligned with each career
- **FR-037**: Mapping MUST specify the exact major or program name to apply under for each career path at each university (e.g., "Aerospace Engineering" at NC State, "Industrial and Systems Engineering with Design Concentration" at Georgia Tech)
- **FR-038**: Guide MUST indicate when a university does not offer a program relevant to a specific career path or only offers partial/related programs
- **FR-039**: Mapping MUST note program strengths, rankings, or unique features where relevant (e.g., "UCLA School of Theater, Film and Television is a top-ranked film program")
- **FR-040**: Guide MUST identify programs with additional admission requirements beyond general university admission (e.g., portfolio requirements for art/design programs)
- **FR-041**: Mapping MUST indicate which universities offer flexibility across multiple career interests if Connor remains undecided

#### Visit Planning (User Story 6)

- **FR-042**: Guide MUST provide optimal timing recommendations for visiting each university (considering academic calendar, application timeline, and visit program availability)
- **FR-043**: Guide MUST include instructions for scheduling official campus tours, information sessions, and special visit opportunities (class observations, overnight stays) for each university
- **FR-044**: Guide MUST provide a standardized visit checklist covering what to observe (facilities, campus culture, student interactions) and questions to ask (about programs, resources, student life, financial aid)
- **FR-045**: Guide MUST include a visit documentation template to record impressions, pros/cons, and observations for later comparison across universities
- **FR-046**: Guide MUST address visit prioritization strategies when visiting all eight schools is not feasible (financial or time constraints)
- **FR-047**: Guide MUST clarify whether demonstrated interest (visiting) impacts admission chances at each university

### Assumptions

- **Assumption 1**: Content will be written and maintained in markdown format for version control and easy updates, then manually formatted in Microsoft Word for final export to both PDF and DOCX formats with professional formatting, table of contents, and page numbering
- **Assumption 2**: The companion spreadsheet data will be maintained as CSV (comma-separated values) files locally with the project for version control and easy updates, with one CSV file per spreadsheet tab (16 total CSV files). The family will manually import these CSV files into Google Sheets for their daily use, which provides cloud-based access, automatic backup, real-time collaboration between Connor and parents, and multi-device accessibility
- **Assumption 3**: The family has access to software capable of viewing and editing common document formats (Word/Google Docs/PDF) and has a Google account for importing CSV files into Google Sheets
- **Assumption 4**: Information will be verified against official university sources and updated monthly (or when significant changes occur) by the family using Claude or AI assistants following the provided update instructions, with updates reflected in both the markdown source files and CSV files which can then be exported to PDF/DOCX and re-imported to Google Sheets
- **Assumption 5**: The guide is personalized for Connor Griffin but structured in a way that could be adapted for other students
- **Assumption 6**: Deadline and requirement information will be accurate as of February 2026 with clearly marked verification dates
- **Assumption 7**: The guide will be accessible to both parents and Connor, using plain language without assuming prior admissions expertise
- **Assumption 8**: The spreadsheet tabs will allow the family to choose their preferred organizational method (by university or by career interest) based on their needs at different stages of the process
- **Assumption 9**: Connor will focus primarily on SAT preparation and testing, with ACT information provided as a backup option if SAT scores are not competitive for his target universities. The timeline and test preparation guidance will prioritize SAT while maintaining flexibility to pivot to ACT if needed.

### Key Entities

#### Core Deliverables

- **Guide Document/PDF**: The comprehensive formatted document containing all narrative content, university profiles, career guides, visit planning instructions, and homeschool requirements with table of contents and navigation
- **Deadline Tracking Spreadsheet**: Multi-tab spreadsheet workbook containing:
  - 8 university-specific tabs (one per target school)
  - 7 career interest tabs (one per career path)
  - 1 master timeline tab (chronological view of all dates)
  - Each tab includes columns for: task/milestone, target date, completion status, notes, responsible party

#### Content Entities

- **Student Profile**: Connor Griffin (age 17, 11th grade, homeschooled entire life, exploring 7 career paths, targeting 8 universities, takes annual standardized tests for tracking)
- **University Profile**: Detailed information for each of 8 target universities (NC State, Duke, UCLA, App State, NC A&T, Georgia Tech, UNC Charlotte, UNC Chapel Hill) including requirements, deadlines, programs, and homeschool-specific policies
- **Homeschool Documentation**: Transcript format requirements, parent-calculated GPA documentation, course descriptions, NC homeschool regulations, third-party validation options (AP exams, dual enrollment, accredited online courses)
- **Career Path**: Comprehensive information for each of 7 careers (business, industrial design, architecture, art, music production, film production, aerospace engineering) including description, skills, day-in-life, outlook
- **Timeline Item**: Month-by-month action items from February 2026 through August 2027 including standardized test dates, application deadlines, decision dates, and homeschool-specific preparation tasks
- **Application Deadline**: Specific dates with deadline type (early action, early decision, regular decision) for each university
- **Program Mapping**: Relationship between career paths and specific university programs/majors, including program strengths and additional requirements
- **Visit Plan**: Structured information for planning and documenting college visits including timing, scheduling, checklists, and documentation templates
- **Recommendation Sources**: Acceptable letter of recommendation providers for homeschool students (outside instructors, tutors, coaches, employers, community leaders) for each university

## Success Criteria *(mandatory)*

### Measurable Outcomes

#### Deliverable Quality

- **SC-001**: The guide is delivered as a complete, formatted document or PDF with table of contents, section headings, page numbers, and professional formatting that can be printed or shared digitally
- **SC-002**: The companion spreadsheet is delivered with all required tabs (8 university tabs + 7 career interest tabs + 1 master timeline tab = minimum 16 tabs) and includes working date tracking functionality
- **SC-003**: Each university tab in the spreadsheet contains all critical deadlines for that specific university, organized chronologically with status tracking capability
- **SC-004**: Each career interest tab in the spreadsheet shows all universities offering programs in that career area with relevant application deadlines and program-specific requirements
- **SC-005**: The master timeline tab consolidates all critical dates from all universities in a single chronological view from February 2026 through August 2027
- **SC-006**: Users can locate any specific deadline in the spreadsheet within 30 seconds using either the university view or career interest view
- **SC-007**: The document/PDF remains readable and navigable when printed (clear page breaks, no cut-off tables, readable fonts)
- **SC-007a**: Following the AI update instructions, the family can successfully use Claude or AI assistants to check all 8 university websites for updated deadlines and requirements, identify changes, and generate updated guide content within 30 minutes of monthly verification
- **SC-007b**: The AI update instructions include example prompts that produce accurate, properly formatted markdown and CSV updates when provided with official university URLs

#### Timeline and Application Success

- **SC-008**: Following the timeline results in meeting 100% of application deadlines for all eight universities with no missed opportunities
- **SC-009**: Connor and parents can identify all required materials for any university application (test scores, essays, supplements) within 5 minutes of reviewing the guide
- **SC-010**: Connor can explain each of the seven career paths (what they do, required skills, job outlook) accurately enough to make an informed decision about his top 3 career interests
- **SC-011**: Parents can identify which universities offer strong programs for any of Connor's career interests within 3 minutes of reviewing the career-university mapping
- **SC-012**: Using the visit planning guide, the family successfully plans and executes visits to at least 5 of the 8 target universities with documented impressions for comparison
- **SC-013**: Connor completes the SAT at optimal times (no later than October 2026 for early applications, December 2026 for regular decision) as indicated by the timeline
- **SC-014**: All deadline dates and requirements remain accurate for at least 90% of information over a 6-month period (verified against official sources)
- **SC-015**: Connor and parents can distinguish between binding (early decision) and non-binding (early action, regular decision) options and make informed choices about application strategy
- **SC-016**: 100% of information in the guide is cited from authoritative sources (official university websites, Common App, College Board, etc.) with verification dates
- **SC-017**: Connor submits complete, on-time applications to all desired universities without missing any school-specific requirements or supplemental materials
- **SC-018**: Parents can prepare a compliant homeschool transcript for each university within 2 hours using the guide's instructions and templates
- **SC-019**: Connor identifies and completes all required homeschool-specific validation (SAT Subject Tests, third-party courses, or portfolio submissions) at least 2 months before application deadlines
