# Data Model: Navigation Structure

**Feature**: GitHub Pages Website with Navigation
**Date**: 2026-02-14
**Purpose**: Define the hierarchical navigation menu structure for the college admissions guide website

---

## Navigation System Overview

The website uses **Just-the-Docs theme's built-in navigation system**, which automatically generates hierarchical navigation based on page front matter rather than a separate YAML file.

### Navigation Approach

**Front Matter-Based Navigation**:
- Each page defines its own navigation properties in YAML front matter
- Just-the-Docs automatically builds the navigation tree
- No separate `_data/navigation.yml` file needed

### Front Matter Schema

Each page includes these navigation properties:

```yaml
---
title: string           # Display name in menu (required)
nav_order: number       # Position within its level (optional, defaults to alphabetical)
parent: string          # Parent page title for 2nd level pages (optional)
grand_parent: string    # Grandparent page title for 3rd level pages (optional)
has_children: boolean   # Set to true if page has child pages (optional)
nav_exclude: boolean    # Set to true to exclude from navigation (optional)
---
```

---

## Navigation Hierarchy

### Level 1: Top-Level Sections

```yaml
# Home (README.md)
---
title: "Home"
nav_order: 1
---

# Timeline Overview
---
title: "Timeline"
nav_order: 2
---

# Universities Section
---
title: "Universities"
nav_order: 3
has_children: true
---

# Homeschool Requirements Section
---
title: "Homeschool Requirements"
nav_order: 4
has_children: true
---

# Research Section
---
title: "Research"
nav_order: 5
has_children: true
---

# Spreadsheets Section
---
title: "Spreadsheets"
nav_order: 6
---
```

### Level 2: Subsections (Parent Relationships)

**Universities Subsection** (8 universities):
```yaml
# NC State
---
title: "NC State"
parent: "Universities"
nav_order: 1
---

# Duke
---
title: "Duke"
parent: "Universities"
nav_order: 2
---

# UCLA
---
title: "UCLA"
parent: "Universities"
nav_order: 3
---

# Appalachian State
---
title: "Appalachian State"
parent: "Universities"
nav_order: 4
---

# NC A&T
---
title: "NC A&T"
parent: "Universities"
nav_order: 5
---

# Georgia Tech
---
title: "Georgia Tech"
parent: "Universities"
nav_order: 6
---

# UNC Charlotte
---
title: "UNC Charlotte"
parent: "Universities"
nav_order: 7
---

# UNC Chapel Hill
---
title: "UNC Chapel Hill"
parent: "Universities"
nav_order: 8
---
```

**Homeschool Requirements Subsection**:
```yaml
# Overview
---
title: "Overview"
parent: "Homeschool Requirements"
nav_order: 1
---

# Transcripts
---
title: "Transcripts"
parent: "Homeschool Requirements"
nav_order: 2
---

# Recommendations
---
title: "Recommendations"
parent: "Homeschool Requirements"
nav_order: 3
---

# Validation
---
title: "Validation"
parent: "Homeschool Requirements"
nav_order: 4
---

# NC Regulations
---
title: "NC Regulations"
parent: "Homeschool Requirements"
nav_order: 5
---

# Transcript Template
---
title: "Transcript Template"
parent: "Homeschool Requirements"
nav_order: 6
---

# Transcript Sample
---
title: "Transcript Sample"
parent: "Homeschool Requirements"
nav_order: 7
---
```

**Research Subsection**:
```yaml
# Testing Calendar
---
title: "Testing Calendar"
parent: "Research"
nav_order: 1
---

# Financial Aid Deadlines
---
title: "Financial Aid Deadlines"
parent: "Research"
nav_order: 2
---

# NC Homeschool Regulations
---
title: "NC Homeschool Regulations"
parent: "Research"
nav_order: 3
---
```

### Level 3: Third-Level Pages (Not currently used)

The guide structure is primarily 2 levels deep. If future content requires 3 levels:

```yaml
# Example third-level page
---
title: "Detailed Subtopic"
parent: "Parent Page Title"
grand_parent: "Grandparent Page Title"
nav_order: 1
---
```

---

## Navigation Features

### Automatic Features (Just-the-Docs)

1. **Active Page Indication**:
   - Current page automatically highlighted
   - Parent/ancestor pages also indicated
   - Uses CSS classes: `.active`, `.nav-list-item.active`

2. **Mobile Hamburger Menu**:
   - Automatically collapses navigation on screens <768px
   - Hamburger icon in top-left
   - Expands/collapses on tap
   - CSS-only implementation (no JavaScript required)

3. **Collapsible Sections**:
   - Parent pages with `has_children: true` get expand/collapse icons
   - Child pages hidden by default, revealed when parent is active or clicked

4. **Breadcrumb Navigation**:
   - Automatically generated for pages with `parent` or `grand_parent`
   - Shows navigation path: Home > Parent > Current Page

---

## Navigation Rendering Logic

Just-the-Docs navigation rendering:

1. **Collect all pages** with navigation properties
2. **Sort by `nav_order`** (or alphabetically if not specified)
3. **Group by hierarchy**:
   - Level 1: Pages with no `parent`
   - Level 2: Pages with `parent` (grouped under parent)
   - Level 3: Pages with `grand_parent` (grouped under parent under grandparent)
4. **Render hierarchical menu** with collapsible sections
5. **Highlight active path** based on current page URL

---

## Implementation Steps

### For Each Content File:

1. **Add front matter** at the top of each markdown file
2. **Set `title`**: Display name for navigation
3. **Set `nav_order`**: Position in menu (optional)
4. **Set `parent`**: For 2nd-level pages (optional)
5. **Set `grand_parent`**: For 3rd-level pages (optional)
6. **Set `has_children`**: For parent pages (optional)

### Special Cases:

**README.md (Homepage)**:
```yaml
---
layout: home
title: "Home"
nav_order: 1
---
```

**Section Landing Pages** (e.g., content/guide/03-universities/README.md):
```yaml
---
title: "Universities"
nav_order: 3
has_children: true
---
```

**Excluded Pages** (not shown in navigation):
```yaml
---
title: "Internal Documentation"
nav_exclude: true
---
```

---

## Mobile Responsiveness

### Breakpoints

- **Mobile**: <768px
  - Hamburger menu
  - Full-screen overlay navigation
  - Touch-friendly tap targets (44px minimum)

- **Tablet**: 768px - 1023px
  - Sidebar navigation (200px width)
  - Collapsible sections

- **Desktop**: 1024px+
  - Full sidebar navigation (250px+ width)
  - Expanded sections by default

### Touch Interactions

- **Tap hamburger icon**: Open/close menu
- **Tap parent page**: Expand/collapse children
- **Tap child page**: Navigate to page, close menu

---

## Success Criteria Validation

This navigation structure satisfies:

- ✅ **SC-001**: Any page accessible in ≤3 clicks
  - Home → Section → Page = 2 clicks
  - Home → Section → Subsection → Page = 3 clicks

- ✅ **SC-005**: All 8 universities accessible in ≤2 clicks
  - Home → Universities = 1 click to expand
  - Universities → Specific University = 2 clicks total

- ✅ **FR-003**: Navigation links to all major sections
  - Home, Timeline, Universities (8 schools), Homeschool Requirements (7 subsections), Research (3 subsections), Spreadsheets

- ✅ **FR-007**: Active page visually indicated
  - Just-the-Docs provides automatic active state styling

- ✅ **FR-002**: Mobile hamburger menu (<768px)
  - Just-the-Docs provides responsive hamburger navigation

---

## File Mapping

Each content file needs front matter added:

### Root Level
- `/README.md` → Home

### Guide Content
- `/content/guide/README.md` → Guide Overview (optional intermediate page)
- `/content/guide/02-timeline-overview.md` → Timeline

### Universities (8 files)
- `/content/guide/03-universities/nc-state.md` → NC State
- `/content/guide/03-universities/duke.md` → Duke
- `/content/guide/03-universities/ucla.md` → UCLA
- `/content/guide/03-universities/appalachian-state.md` → Appalachian State
- `/content/guide/03-universities/nc-at.md` → NC A&T
- `/content/guide/03-universities/georgia-tech.md` → Georgia Tech
- `/content/guide/03-universities/unc-charlotte.md` → UNC Charlotte
- `/content/guide/03-universities/unc-chapel-hill.md` → UNC Chapel Hill

### Homeschool Requirements (7 files)
- `/content/guide/04-homeschool-requirements/overview.md` → Overview
- `/content/guide/04-homeschool-requirements/transcripts.md` → Transcripts
- `/content/guide/04-homeschool-requirements/recommendations.md` → Recommendations
- `/content/guide/04-homeschool-requirements/validation.md` → Validation
- `/content/guide/04-homeschool-requirements/nc-regulations.md` → NC Regulations
- `/content/guide/04-homeschool-requirements/transcript-template.md` → Transcript Template
- `/content/guide/04-homeschool-requirements/transcript-sample.md` → Transcript Sample

### Research (3 files)
- `/research/testing-calendar.md` → Testing Calendar
- `/research/financial-aid-deadlines.md` → Financial Aid Deadlines
- `/research/nc-homeschool-regulations.md` → NC Homeschool Regulations

### Spreadsheets
- `/spreadsheets/import-instructions.md` → Spreadsheets

---

**File Location**: `/home/shgriffi/dev/college/connor/specs/003-github-pages-site/data-model.md`
**Related Files**:
- [Feature Specification](spec.md)
- [Implementation Plan](plan.md)
- [Research Document](research.md)
- [Task List](tasks.md)
