# Implementation Plan: GitHub Pages Website with Navigation

**Branch**: `003-github-pages-site` | **Date**: 2026-02-14 | **Spec**: [spec.md](./spec.md)
**Input**: Feature specification from `/specs/003-github-pages-site/spec.md`

## Summary

Transform the existing college admissions guide markdown content into a professional, navigable GitHub Pages website. Deploy using Jekyll with a documentation-focused theme (Minimal Architect or similar), implement hierarchical navigation menu with mobile-responsive hamburger pattern, standardize all internal links to root-relative paths, and configure deployment from main branch. No file reorganization required - all existing content remains in current structure.

## Technical Context

**Language/Version**: Jekyll 3.9+ (GitHub Pages compatible), Liquid templating
**Primary Dependencies**:
- Jekyll (static site generator, GitHub Pages default)
- Minimal Architect theme or similar documentation theme (GitHub Pages compatible)
- GitHub Pages gem (provides Jekyll plugins and dependencies)

**Storage**: Static files (Markdown → HTML), no database
**Testing**: Local Jekyll server (`bundle exec jekyll serve`), link validation, responsive design testing
**Target Platform**: GitHub Pages (static hosting), browsers (Chrome, Firefox, Safari, Edge - last 2 years)
**Project Type**: Static website (Jekyll-based documentation site)
**Performance Goals**:
- Page load time <3 seconds on standard broadband
- Mobile responsive (320px - 1920px)
- Zero 404 errors on internal links

**Constraints**:
- Must deploy from main branch (no gh-pages branch)
- Must maintain existing file structure (FR-011)
- Must use README.md as homepage without duplication (FR-008)
- GitHub Pages limitations: Jekyll only, specific plugin whitelist, no custom Ruby code

**Scale/Scope**:
- ~60 pages of markdown content
- 8 university profiles
- 16 CSV files
- 3-level navigation hierarchy (sections → subsections → pages)
- Hierarchical navigation menu with 5 top-level sections

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

### Alignment with Core Principles

**I. Accessibility** ✅ PASS
- Converting markdown to formatted HTML improves readability (visual hierarchy, proper typography)
- Mobile-responsive design ensures access on all devices (320px+)
- Hamburger menu on mobile follows standard UX patterns (familiar to users)
- No accessibility regressions: all existing plain-language content preserved

**II. Accuracy** ✅ PASS
- No content changes - only presentation layer
- All existing citations and verification dates preserved
- Links standardized to root-relative paths improve reliability (100% internal link success rate per SC-002)

**III. Comprehensiveness** ✅ PASS
- All existing content remains accessible
- Navigation menu provides clear overview of complete guide structure
- CSV downloads maintained (deadline tracking tools)
- No content removed or hidden

**IV. Actionability** ✅ PASS
- **Improved** actionability: hierarchical navigation reduces clicks to reach any section (3 clicks max per SC-001)
- Spreadsheet section links directly to CSV files (1-click download per SC-008)
- Mobile access enables families to reference guide from any location

**V. Inclusivity** ✅ PASS
- Free hosting (GitHub Pages) removes cost barrier
- Mobile-first design supports families without desktop computers
- No authentication required maintains universal access
- Existing diverse content examples preserved

**Verdict**: ✅ ALL GATES PASS - Feature enhances accessibility and actionability without compromising other principles.

## Project Structure

### Documentation (this feature)

```text
specs/003-github-pages-site/
├── plan.md              # This file (/speckit.plan output)
├── research.md          # Phase 0: Jekyll themes, navigation patterns
├── data-model.md        # Phase 1: Navigation structure (YAML schema)
├── quickstart.md        # Phase 1: Local testing & deployment guide
└── contracts/           # N/A for static site (no APIs)
```

### Source Code (repository root)

```text
# Jekyll Configuration Files
_config.yml              # Main Jekyll configuration
_data/
  └── navigation.yml     # Hierarchical navigation menu structure

# Jekyll Layouts & Includes
_layouts/
  ├── default.html       # Base page template (from theme, customized if needed)
  └── page.html          # Content page template (from theme, customized if needed)

_includes/
  ├── header.html        # Site header with navigation (theme override)
  ├── nav-menu.html      # Navigation menu component (mobile + desktop)
  └── footer.html        # Site footer (theme override if needed)

# Jekyll Assets (if theme customization needed)
_sass/
  └── custom.scss        # Custom styles (navigation, responsive tweaks)

assets/
  ├── css/
  │   └── style.scss     # Main stylesheet (imports theme + custom)
  └── js/
      └── menu.js        # Hamburger menu toggle (if not provided by theme)

# Existing Content (NO CHANGES to file locations)
README.md                # Homepage (used as index via Jekyll config)
content/
  └── guide/
      ├── README.md
      ├── 02-timeline-overview.md
      ├── 03-universities/
      │   ├── nc-state.md
      │   ├── duke.md
      │   └── ... (6 more)
      └── 04-homeschool-requirements/
          ├── overview.md
          └── ... (6 more)

spreadsheets/
  ├── master-timeline.csv
  └── ... (15 more CSVs)

research/
  └── ... (existing research files)

# GitHub Pages Essentials
Gemfile                  # Ruby dependencies (Jekyll, theme)
Gemfile.lock             # Locked dependency versions
.gitignore               # Ignore _site/, .jekyll-cache/
```

**Structure Decision**: Minimal Jekyll overlay on existing repository. No reorganization of content files. Jekyll configuration lives in root, with `_config.yml` pointing to existing README.md as index and existing content structure preserved. Theme-based approach minimizes custom code.

## Complexity Tracking

**No violations** - All constitution checks pass. This table is not needed.

---

## Phase 0: Research & Technology Selection

### Research Tasks

1. **Jekyll Theme Selection**
   - Evaluate GitHub Pages-compatible documentation themes
   - Criteria: Built-in navigation support, mobile responsive, minimal customization needed
   - Candidates: Minimal Architect, Just-the-Docs, Cayman, Minimal Mistakes
   - Decision: Document chosen theme with rationale

2. **Navigation Implementation Patterns**
   - Research Jekyll navigation YAML structures
   - Evaluate hamburger menu implementations (CSS-only vs. minimal JS)
   - Best practices for 3-level hierarchical menus
   - Active page indication techniques

3. **GitHub Pages Configuration**
   - Verify main branch deployment configuration
   - Document Jekyll plugin whitelist (GitHub Pages restrictions)
   - Research using README.md as index page in Jekyll
   - Best practices for root-relative link handling in Jekyll

4. **Link Migration Strategy**
   - Assess current link formats in existing markdown files
   - Determine automation approach for converting to root-relative paths
   - Verify Jekyll's URL handling for `.md` → `.html` conversion

### Output Artifact

**File**: `research.md`

**Structure**:
```markdown
# Research: GitHub Pages Website Implementation

## 1. Jekyll Theme Decision

**Decision**: [Chosen theme name]
**Rationale**: [Why this theme]
**Alternatives Considered**: [Other themes evaluated]
**Installation**: [How to add to Gemfile and _config.yml]

## 2. Navigation Structure

**Decision**: [YAML-based navigation in _data/navigation.yml]
**Rationale**: [Separation of content and structure]
**Pattern**: [Hierarchical nested structure]
**Mobile Implementation**: [CSS-only hamburger or minimal JS]

## 3. Deployment Configuration

**Decision**: [Main branch, root directory]
**Configuration Steps**: [Enable Pages, set source]
**Validation**: [How to verify deployment]

## 4. Link Standardization

**Current State**: [Mix of relative and markdown-specific links]
**Target State**: [Root-relative paths]
**Migration Approach**: [Manual or scripted find/replace]
**Testing**: [Link validation tools]
```

---

## Phase 1: Design & Configuration

### 1. Data Model: Navigation Structure

**File**: `data-model.md`

**Purpose**: Define the hierarchical navigation menu structure used in `_data/navigation.yml`

**Schema**:
```yaml
# Navigation Item Schema
- title: string          # Display name in menu
  url: string           # Root-relative path (e.g., /content/guide/02-timeline-overview)
  children: array       # Optional nested items
    - title: string
      url: string
      children: array   # Can nest 3 levels deep
```

**Example Structure**:
```yaml
navigation:
  - title: Home
    url: /

  - title: Timeline
    url: /content/guide/02-timeline-overview

  - title: Universities
    url: /content/guide/03-universities/
    children:
      - title: NC State
        url: /content/guide/03-universities/nc-state
      - title: Duke
        url: /content/guide/03-universities/duke
      # ... (6 more)

  - title: Homeschool Requirements
    url: /content/guide/04-homeschool-requirements/overview
    children:
      - title: Transcripts
        url: /content/guide/04-homeschool-requirements/transcripts
      - title: Recommendations
        url: /content/guide/04-homeschool-requirements/recommendations
      # ... (4 more)

  - title: Research
    url: /research/
    children:
      - title: Testing Calendar
        url: /research/testing-calendar
      - title: Financial Aid
        url: /research/financial-aid-deadlines
      - title: NC Regulations
        url: /research/nc-homeschool-regulations

  - title: Spreadsheets
    url: /spreadsheets/import-instructions
```

### 2. Contracts

**N/A** - Static website has no API contracts. Navigation structure documented in data-model.md.

### 3. Quickstart Guide

**File**: `quickstart.md`

**Purpose**: Local development setup and deployment instructions

**Sections**:
1. Prerequisites (Ruby, Bundler)
2. Local Setup (`bundle install`, `bundle exec jekyll serve`)
3. Testing Checklist (navigation, mobile responsive, links)
4. Deployment (Enable GitHub Pages, verify build)
5. Troubleshooting (common Jekyll errors, GitHub Pages build failures)

---

## Implementation Phases (Post-Planning)

*These will be detailed in tasks.md via `/speckit.tasks` command*

### Phase 1: Jekyll Setup & Configuration
- Create _config.yml with theme and site settings
- Create Gemfile with Jekyll and theme dependencies
- Configure README.md as index page
- Set permalink structure for clean URLs

### Phase 2: Navigation Implementation
- Create _data/navigation.yml with hierarchical structure
- Implement nav-menu include (or customize theme's navigation)
- Add hamburger menu toggle for mobile (<768px)
- Implement active page indication

### Phase 3: Theme Customization
- Override layouts if needed (header/footer)
- Add custom CSS for navigation refinements
- Ensure mobile responsiveness (320px - 1920px)
- Configure external link target="_blank"

### Phase 4: Link Standardization
- Audit all markdown files for internal links
- Convert relative links to root-relative paths
- Test all internal links (verify no 404s)
- Ensure CSV files remain downloadable

### Phase 5: Testing & Deployment
- Local testing across screen sizes
- Link validation (100% success rate)
- Enable GitHub Pages on main branch
- Verify deployment and fix any build errors
- Final cross-browser testing

---

## Success Metrics (from spec.md)

- ✅ SC-001: Navigate to any section in ≤3 clicks
- ✅ SC-002: 100% internal links work without 404s
- ✅ SC-003: Homepage loads in <3 seconds
- ✅ SC-004: Navigation usable on 320px - 1920px screens
- ✅ SC-005: Access all 8 universities in ≤2 clicks
- ✅ SC-006: 100% external links open in new tabs
- ✅ SC-007: Deploy to GitHub Pages with zero errors
- ✅ SC-008: All CSVs downloadable in 1 click

---

## Next Steps

1. **Execute**: Run `/speckit.tasks` to generate detailed task breakdown
2. **Implement**: Follow task sequence from tasks.md
3. **Deploy**: Enable GitHub Pages and verify live site
4. **Validate**: Test all success criteria post-deployment
