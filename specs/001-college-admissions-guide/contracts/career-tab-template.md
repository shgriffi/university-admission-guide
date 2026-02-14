# Career Interest Tab Template

**Purpose**: Structure for each of the 7 career-specific spreadsheet tabs to show which universities offer programs in each career area

**Tab Names**:
- Business
- Industrial Design
- Architecture
- Art
- Music Production
- Film Production
- Aerospace Engineering

---

## Column Structure

| Column | Name | Type | Description | Validation Rules |
|--------|------|------|-------------|------------------|
| A | University | Text | Name of target university | From list of 8 universities |
| B | Program Offered | Dropdown | Whether program is available | Dropdown: Yes, No, Partial/Related |
| C | Program Name | Text | Exact major/program title | Required if Program Offered = "Yes" |
| D | Department/School | Text | Which college/school houses the program | Optional |
| E | Application Deadline (EA) | Date | Early Action deadline | Date format MM/DD/YYYY, N/A if not offered |
| F | Application Deadline (ED) | Date | Early Decision deadline | Date format MM/DD/YYYY, N/A if not offered |
| G | Application Deadline (RD) | Date | Regular Decision deadline | Date format MM/DD/YYYY |
| H | Additional Requirements | Text | Portfolio, audition, extra essays, etc. | Optional, max 300 chars |
| I | Program Strength | Dropdown | Reputation indicator | Dropdown: Top-Ranked, Strong, Average, Unknown |
| J | Notes | Text | Unique features, rankings, considerations | Optional, max 500 chars |

---

## Row Content (One Row Per University)

Each career tab contains exactly 8 rows (one for each target university):

1. NC State
2. Duke
3. UCLA
4. App State
5. NC A&T
6. Georgia Tech
7. UNC Charlotte
8. UNC Chapel Hill

---

## Conditional Formatting

**Program Not Offered** (Program Offered = "No"):
- Background: Light red (#FFEEEE)
- Text color: Gray (#999999)

**Top-Ranked Program** (Program Strength = "Top-Ranked"):
- Background: Light green (#CCFFCC)
- Font: Bold

**Program Offered** (Program Offered = "Yes"):
- Background: White
- Font: Normal

**Partial/Related Program** (Program Offered = "Partial/Related"):
- Background: Light yellow (#FFFFEE)
- Font: Italic

---

## Default Sort Order

Primary: Application Deadline (RD) - ascending (soonest first)
Secondary: Program Strength (Top-Ranked > Strong > Average > Unknown)

---

## Freeze Panes

Freeze first row (header row) for scrolling

---

## Example Data: Aerospace Engineering Tab

| University | Program Offered | Program Name | Department/School | Application Deadline (EA) | Application Deadline (ED) | Application Deadline (RD) | Additional Requirements | Program Strength | Notes |
|------------|-----------------|--------------|-------------------|---------------------------|---------------------------|---------------------------|-------------------------|------------------|-------|
| NC State | Yes | Aerospace Engineering | College of Engineering | 10/15/2026 | N/A | 01/15/2027 | None | Strong | ABET-accredited, co-op opportunities |
| Duke | No | - | - | N/A | N/A | N/A | - | N/A | No engineering program; consider Mechanical Engineering |
| UCLA | Yes | Aerospace Engineering | Samueli School of Engineering | N/A | N/A | 11/30/2026 | UC application | Top-Ranked | Highly competitive, OOS applicant |
| App State | No | - | - | N/A | N/A | N/A | - | N/A | No aerospace program available |
| NC A&T | No | - | - | N/A | N/A | N/A | - | N/A | Mechanical Engineering available as alternative |
| Georgia Tech | Yes | Aerospace Engineering | Daniel Guggenheim School | N/A | N/A | 01/04/2027 | None | Top-Ranked | #2 ranked program nationally (U.S. News) |
| UNC Charlotte | No | - | - | N/A | N/A | N/A | - | N/A | Mechanical Engineering available |
| UNC Chapel Hill | No | - | - | N/A | N/A | N/A | - | N/A | No engineering school |

---

## Example Data: Film Production Tab

| University | Program Offered | Program Name | Department/School | Application Deadline (EA) | Application Deadline (ED) | Application Deadline (RD) | Additional Requirements | Program Strength | Notes |
|------------|-----------------|--------------|-------------------|---------------------------|---------------------------|---------------------------|-------------------------|------------------|-------|
| NC State | Partial/Related | Communication Media | College of Humanities and Social Sciences | 10/15/2026 | N/A | 01/15/2027 | None | Average | Not dedicated film program |
| Duke | Yes | Visual and Media Studies | Trinity College of Arts & Sciences | N/A | 11/01/2026 | 01/02/2027 | Supplemental essay | Strong | Documentary emphasis |
| UCLA | Yes | Film and Television | School of Theater, Film and Television | N/A | N/A | 11/30/2026 | Portfolio, creative sample | Top-Ranked | #1 film school, highly selective |
| App State | Partial/Related | Communication Studies (Media Production) | College of Fine and Applied Arts | 11/01/2026 | N/A | 02/01/2027 | None | Average | Focus on broadcast media |
| NC A&T | No | - | - | N/A | N/A | N/A | - | N/A | Communication available, not film-specific |
| Georgia Tech | No | - | - | N/A | N/A | N/A | - | N/A | No film production program |
| UNC Charlotte | Partial/Related | Film Studies | College of Liberal Arts & Sciences | 11/01/2026 | N/A | 06/01/2027 | None | Average | Theory-focused, limited production |
| UNC Chapel Hill | Yes | Media and Journalism (Film Concentration) | Hussman School of Journalism and Media | 10/15/2026 | 11/01/2026 | 01/15/2027 | Portfolio recommended | Strong | Combines journalism with film |

---

## Tab-Specific Customization

Each career tab should include:

1. **Header section** (above column headers):
   - Career path name
   - Brief description (1-2 sentences about the career)
   - Link to full career guide section in main document

2. **Summary section** (below data rows):
   - Universities offering program: COUNT where "Program Offered" = "Yes"
   - Top-ranked options: COUNT where "Program Strength" = "Top-Ranked"
   - Programs requiring portfolios/auditions: COUNT where "Additional Requirements" contains text
   - Earliest deadline: MIN of all deadline columns

3. **Legend/Key** (in separate cells):
   - Color coding explanation
   - Program Strength definitions
   - Partial/Related explanation

---

## Filter and Sort Features

- Enable filter buttons on header row
- Create custom views:
  - **View 1**: Only universities offering program (Program Offered = "Yes")
  - **View 2**: Sorted by deadline (soonest first)
  - **View 3**: Sorted by program strength (best first)

---

## Cross-Reference Links

In the Notes column, include hyperlinks to:
- University tab for that university (for full deadline details)
- Program website (for official information)
- Admissions requirements page

---

## Notes for Implementation

- Populate from Phase 0 research (RT-006 program mapping matrix)
- Verify all program names against official university catalogs
- Update deadline dates from university tabs to ensure consistency
- Consider adding "Apply?" column for Connor to mark his decisions
- Print settings: Portrait orientation, fit to 1 page

---

**Last Updated**: 2026-02-13
**Template Version**: 1.0
