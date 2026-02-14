# Implementation Tasks: GitHub Pages Website with Navigation

**Feature**: GitHub Pages Website with Navigation
**Branch**: `003-github-pages-site`
**Date**: 2026-02-14
**Spec**: [spec.md](./spec.md) | **Plan**: [plan.md](./plan.md)

---

## Overview

This document provides an actionable, dependency-ordered task list for implementing the GitHub Pages website feature. Tasks are organized by user story priority to enable independent implementation and testing of each increment.

### User Stories (Priority Order)

1. **User Story 1 (P1)**: View Guide as Website - Core value proposition
2. **User Story 2 (P2)**: Navigate Between Topics Using Menu - Navigation menu
3. **User Story 3 (P3)**: Navigate Between Related Pages - Internal links

### Implementation Strategy

- **MVP Scope**: User Story 1 (P1) - Provides basic website functionality
- **Incremental Delivery**: Each user story is independently testable
- **Parallel Opportunities**: Tasks marked with [P] can run in parallel

---

## Phase 1: Setup

**Goal**: Initialize project structure and dependencies

### Tasks

- [X] T001 Create .gitignore file for Jekyll build artifacts at /.gitignore
- [X] T002 Create Gemfile with Jekyll and GitHub Pages dependencies at /Gemfile
- [X] T003 Create basic _config.yml with site settings at /_config.yml
- [X] T004 Create Jekyll directory structure (_layouts/, _includes/, _data/, _sass/, assets/)
- [X] T005 ~~Run bundle install~~ **SKIPPED** - Using GitHub Pages auto-build (no local setup)

**Completion Criteria**: Project structure initialized, ready for GitHub Pages (no local Ruby/Bundler required)

---

## Phase 2: Foundational (Blocking Prerequisites)

**Goal**: Set up theme and basic configuration needed for all user stories

### Tasks

- [X] T006 Research and select Jekyll theme (Minimal Architect, Just-the-Docs, or similar)
- [X] T007 Document theme decision in specs/003-github-pages-site/research.md
- [X] T008 Add theme to Gemfile and _config.yml (changed to remote_theme for GitHub Pages)
- [X] T009 Configure _config.yml to use README.md as index page (FR-008)
- [X] T010 Configure permalink structure for clean URLs in _config.yml
- [X] T011 ~~Test basic Jekyll build~~ **SKIPPED** - Testing on live GitHub Pages instead

**Completion Criteria**: Theme selected, configuration complete, ready for GitHub Pages deployment

---

## Phase 3: User Story 1 (P1) - View Guide as Website

**Story Goal**: Transform markdown files into a professional, formatted website

**Independent Test**: Visit GitHub Pages URL and verify homepage displays with formatted content, proper styling, and responsive layout

### Tasks

- [X] T012 [P] [US1] Create default layout template at /_layouts/default.html
- [X] T013 [P] [US1] Create page layout template at /_layouts/page.html
- [X] T014 [P] [US1] Create header include at /_includes/header.html
- [X] T015 [P] [US1] Create footer include at /_includes/footer.html
- [X] T016 [US1] Create main stylesheet at /assets/css/style.scss (imports theme + custom)
- [X] T017 [US1] Create custom SCSS for responsive design at /_sass/custom.scss
- [X] T018 [US1] Configure responsive viewport meta tags in layouts (320px - 1920px)
- [X] T019 [US1] Add CSS for mobile responsiveness (media queries, flexible layouts)
- [ ] T020 [US1] ~~Test local build~~ **MOVED** - Will test on GitHub Pages after deployment (T057)
- [ ] T021 [US1] ~~Test responsive design locally~~ **MOVED** - Will test on GitHub Pages (T056)
- [ ] T022 [US1] ~~Verify markdown formatting locally~~ **MOVED** - Will test on GitHub Pages (T057)

**Acceptance Criteria**:
- ✅ Homepage loads with formatted content (SC-003: <3 seconds) - Test on GitHub Pages
- ✅ All markdown formatting renders correctly (headers, lists, tables, links) - Test on GitHub Pages
- ✅ Layout is responsive from 320px to 1920px screens (SC-004) - Test on GitHub Pages
- ✅ Site builds without errors on GitHub Pages

**Files Modified**: README.md (frontmatter only), _layouts/, _includes/, assets/, _sass/

---

## Phase 4: User Story 2 (P2) - Navigate Between Topics Using Menu

**Story Goal**: Implement hierarchical navigation menu with mobile hamburger pattern

**Independent Test**: Click any menu item from any page and verify navigation works; test hamburger menu on mobile

### Tasks

- [X] T023 [US2] Create navigation data model document at /specs/003-github-pages-site/data-model.md
- [ ] T024 [US2] Create navigation YAML structure at /_data/navigation.yml
- [ ] T025 [US2] Populate navigation.yml with all major sections (Home, Timeline, Universities, Homeschool Requirements, Research, Spreadsheets)
- [ ] T026 [US2] Add all 8 university profiles to Universities submenu in navigation.yml
- [ ] T027 [US2] Add all homeschool subsections to Homeschool Requirements submenu in navigation.yml
- [ ] T028 [US2] Create navigation menu component at /_includes/nav-menu.html
- [ ] T029 [US2] Implement 3-level hierarchical menu rendering (sections → subsections → pages)
- [ ] T030 [US2] Create hamburger menu JavaScript at /assets/js/menu.js
- [ ] T031 [US2] Add hamburger menu toggle functionality for mobile (<768px)
- [ ] T032 [US2] Implement active page indication (highlight current section)
- [ ] T033 [US2] Style navigation menu (desktop full menu, mobile hamburger)
- [ ] T034 [US2] Add CSS media queries for mobile navigation (<768px)
- [ ] T035 [US2] Update header include to use nav-menu component
- [ ] T036 [US2] Test navigation menu on desktop (all items visible and clickable)
- [ ] T037 [US2] Test hamburger menu on mobile (collapses, expands on tap)
- [ ] T038 [US2] Verify active page indication works correctly

**Acceptance Criteria**:
- ✅ Navigation menu visible on all pages with all major sections (FR-003)
- ✅ All 8 universities accessible from menu in ≤2 clicks (SC-005)
- ✅ Current section visually indicated (FR-007)
- ✅ Mobile menu uses hamburger pattern (<768px, FR-002)
- ✅ Any section accessible in ≤3 clicks (SC-001)
- ✅ Menu usable on 320px - 1920px screens (SC-004)

**Files Modified**: _data/navigation.yml, _includes/nav-menu.html, _includes/header.html, assets/js/menu.js, _sass/custom.scss

---

## Phase 5: User Story 3 (P3) - Navigate Between Related Pages

**Story Goal**: Standardize internal links to enable seamless navigation between related pages

**Independent Test**: Click internal links from any page and verify navigation; test CSV downloads

### Tasks

- [ ] T039 [US3] Audit all markdown files for internal links (use grep or similar)
- [ ] T040 [US3] Document current link formats and target state in specs/003-github-pages-site/research.md
- [ ] T041 [US3] Convert internal links to root-relative paths in /content/guide/README.md
- [ ] T042 [P] [US3] Convert internal links to root-relative paths in /content/guide/02-timeline-overview.md
- [ ] T043 [P] [US3] Convert internal links to root-relative paths in /content/guide/03-universities/*.md (8 files)
- [ ] T044 [P] [US3] Convert internal links to root-relative paths in /content/guide/04-homeschool-requirements/*.md
- [ ] T045 [P] [US3] Convert internal links to root-relative paths in /research/*.md
- [ ] T046 [P] [US3] Convert internal links to root-relative paths in /README.md
- [ ] T047 [P] [US3] Convert internal links to root-relative paths in /spreadsheets/import-instructions.md
- [ ] T048 [US3] Configure external links to open in new tabs (add target="_blank" via Liquid or JavaScript)
- [ ] T049 [US3] Create link validation script or use HTML Proofer gem
- [ ] T050 [US3] Test all internal links for 404 errors (100% success rate)
- [ ] T051 [US3] Verify CSV files are downloadable (test all 16 files)
- [ ] T052 [US3] Test external links open in new tabs without breaking navigation

**Acceptance Criteria**:
- ✅ 100% of internal links navigate correctly without 404s (SC-002, FR-004)
- ✅ All CSV files downloadable in 1 click (SC-008, FR-009)
- ✅ 100% of external links open in new tabs (SC-006, FR-012)
- ✅ Links work in both repository view and GitHub Pages

**Files Modified**: All markdown files in /content/, /research/, /spreadsheets/, README.md

---

## Phase 6: Polish & Deployment

**Goal**: Optimize performance, validate, and deploy to GitHub Pages

### Tasks

- [X] T053 [P] Create quickstart guide at /specs/003-github-pages-site/quickstart.md
- [X] T054 [P] Document local development setup (Ruby, Bundler, Jekyll commands)
- [X] T055 [P] Create testing checklist in quickstart.md (navigation, responsive, links)
- [ ] T056 Comprehensive responsive testing (320px, 480px, 768px, 1024px, 1920px)
- [ ] T057 Performance testing - verify homepage loads in <3 seconds (SC-003)
- [ ] T058 Run link validation - confirm 100% internal link success (SC-002)
- [ ] T059 Cross-browser testing (Chrome, Firefox, Safari, Edge)
- [ ] T060 Optimize images and assets if needed for performance
- [X] T061 Create GitHub Pages deployment checklist in quickstart.md
- [ ] T062 Enable GitHub Pages on main branch via repository settings
- [ ] T063 Configure GitHub Pages source to main branch, root directory
- [ ] T064 Monitor GitHub Pages build - verify zero deployment errors (SC-007)
- [ ] T065 Verify live site URL is accessible and displays correctly
- [ ] T066 Final validation of all success criteria (SC-001 through SC-008)

**Completion Criteria**:
- ✅ Website successfully deploys to GitHub Pages with zero errors (SC-007)
- ✅ All success criteria validated (SC-001 through SC-008)
- ✅ Quickstart guide complete with setup and deployment instructions
- ✅ Performance targets met (<3 second load, SC-003)

**Files Created**: specs/003-github-pages-site/quickstart.md

---

## Task Dependencies

### Critical Path (Sequential)

```text
Phase 1 (Setup)
  ↓
Phase 2 (Foundational) ← BLOCKER for all user stories
  ↓
Phase 3 (US1) ← MVP, can deploy independently
  ↓
Phase 4 (US2) ← Adds navigation, depends on US1 layouts
  ↓
Phase 5 (US3) ← Adds internal links, depends on US2 navigation
  ↓
Phase 6 (Polish & Deployment)
```

### User Story Independence

- **US1 (P1)**: Can be implemented and deployed independently (MVP)
- **US2 (P2)**: Requires US1 layouts but can be tested independently
- **US3 (P3)**: Benefits from US2 menu but can be tested independently

### Parallel Execution Opportunities

**Phase 3 (US1) - Parallel Layout Creation**:
```bash
# Can run in parallel (different files, no dependencies)
T012, T013, T014, T015
```

**Phase 5 (US3) - Parallel Link Conversion**:
```bash
# Can run in parallel (different files)
T042, T043, T044, T045, T046, T047
```

**Phase 6 (Polish) - Parallel Documentation**:
```bash
# Can run in parallel (different concerns)
T053, T054, T055
```

---

## Implementation Notes

### MVP Delivery (User Story 1 Only)

To deliver the minimum viable product, complete only:
- Phase 1: Setup (T001-T005)
- Phase 2: Foundational (T006-T011)
- Phase 3: User Story 1 (T012-T022)
- Phase 6: Deployment subset (T062-T066)

This provides a functional website with formatted content and responsive design.

### Incremental Delivery

Each user story can be deployed as an increment:
1. **Increment 1 (MVP)**: US1 - Formatted website
2. **Increment 2**: US1 + US2 - Add navigation menu
3. **Increment 3**: US1 + US2 + US3 - Add internal link navigation (complete)

### Testing Strategy

- **Local Testing**: Use `bundle exec jekyll serve` to test locally before deployment
- **Responsive Testing**: Use browser dev tools to test multiple screen sizes
- **Link Validation**: Use HTML Proofer gem or manual verification
- **Performance**: Use browser dev tools Network tab to measure load times

### Jekyll-Specific Considerations

- **Plugin Limitations**: GitHub Pages only allows whitelisted Jekyll plugins
- **Build Time**: Jekyll builds locally to validate before pushing
- **Liquid Templating**: Use Liquid syntax for dynamic navigation and active page indication
- **Markdown Rendering**: GitHub Pages uses Kramdown by default

---

## Success Metrics Validation

After completing all tasks, validate these success criteria:

- [ ] **SC-001**: Users can navigate from any page to any other major section in 3 clicks or fewer
- [ ] **SC-002**: 100% of internal markdown links navigate correctly without 404 errors
- [ ] **SC-003**: Website loads and displays homepage content within 3 seconds
- [ ] **SC-004**: Navigation menu is usable and functional on screens from 320px to 1920px
- [ ] **SC-005**: Users can access all 8 university profiles from the navigation menu within 2 clicks
- [ ] **SC-006**: 100% of external links open in new tabs without breaking current page navigation
- [ ] **SC-007**: Website successfully deploys to GitHub Pages with zero configuration errors
- [ ] **SC-008**: All CSV files are downloadable with a single click from the appropriate section

---

## Task Summary

- **Total Tasks**: 66
- **Setup Tasks**: 5 (T001-T005)
- **Foundational Tasks**: 6 (T006-T011)
- **User Story 1 Tasks**: 11 (T012-T022)
- **User Story 2 Tasks**: 16 (T023-T038)
- **User Story 3 Tasks**: 14 (T039-T052)
- **Polish & Deployment Tasks**: 14 (T053-T066)
- **Parallelizable Tasks**: 12 (marked with [P])

**Next Step**: Begin implementation with Phase 1 setup tasks, or run `/speckit.implement` to execute the task plan.

---

**File Location**: `/home/shgriffi/dev/college/connor/specs/003-github-pages-site/tasks.md`
**Related Files**:
- [Feature Specification](spec.md)
- [Implementation Plan](plan.md)
- [Checklists](checklists/)
