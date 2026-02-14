---
layout: home
title: "Home"
nav_order: 1
---

# Comprehensive College Admissions Guide for Homeschool Students

A complete, customizable template for college admissions planning specifically designed for homeschool families. This guide provides an 18-month roadmap from junior year spring through college enrollment, with detailed guidance on homeschool-specific requirements, university profiles, and deadline tracking.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 📚 What's Included

This repository contains a **complete college admissions planning system** with:

### 📖 **Comprehensive Guide** (~60+ pages)
- **18-Month Timeline**: Month-by-month roadmap from February 2026 through August 2027
- **8 University Profiles**: Detailed profiles for NC State, Duke, UCLA, Appalachian State, NC A&T, Georgia Tech, UNC Charlotte, UNC Chapel Hill
- **Homeschool-Specific Guidance**: Transcript preparation, recommendations, validation strategies, NC regulations
- **Testing Calendar**: SAT/ACT test dates, registration deadlines, score release dates (2026-2027)
- **Financial Aid Timeline**: FAFSA, CSS Profile deadlines and requirements

### 📊 **Deadline Tracking System** (16 CSV files)
- **8 University Deadline Files**: Application, financial aid, and decision dates per school
- **7 Career Interest Files**: Placeholder structure for tracking program-specific deadlines
- **1 Master Timeline**: Consolidated view of all critical deadlines in chronological order
- **Google Sheets Import Instructions**: Step-by-step guide for creating a tracking spreadsheet

### 📝 **Templates & Resources**
- **Transcript Template**: Fillable homeschool transcript template
- **Sample Transcript**: Anonymized example showing proper formatting
- **Email Templates**: Sample recommendation request emails
- **Checklists**: Action items and verification checklists throughout

---

## 🚀 Quick Start

### For Families Using This Guide

1. **Start Here**: Go to [`content/guide/README.md`](content/guide/README.md) - this is your main navigation hub
2. **Review the Timeline**: Read [`content/guide/02-timeline-overview.md`](content/guide/02-timeline-overview.md) to see the full 18-month roadmap
3. **Set Up Deadline Tracking**: Follow [`spreadsheets/import-instructions.md`](spreadsheets/import-instructions.md) to create your Google Sheets tracker
4. **Customize for Your Student**: Replace all `[Student Name]`, `[Your Homeschool Name]`, and `[YEAR]` placeholders with your information

### Repository Structure

```
.
├── content/
│   └── guide/
│       ├── README.md                    # 📍 START HERE - Main navigation
│       ├── 02-timeline-overview.md      # 18-month timeline
│       ├── 03-universities/             # 8 university profiles
│       │   ├── nc-state.md
│       │   ├── duke.md
│       │   ├── ucla.md
│       │   └── ... (5 more)
│       └── 04-homeschool-requirements/  # Homeschool guidance
│           ├── overview.md
│           ├── transcripts.md
│           ├── recommendations.md
│           ├── validation.md
│           ├── nc-regulations.md
│           ├── transcript-template.md
│           └── transcript-sample.md
│
├── spreadsheets/
│   ├── master-timeline.csv              # Master deadline tracker
│   ├── nc-state.csv                     # University deadlines (8 files)
│   ├── business.csv                     # Career deadlines (7 files)
│   └── import-instructions.md           # Google Sheets setup guide
│
├── research/
│   ├── sources/                         # University research files
│   ├── testing-calendar.md              # SAT/ACT dates 2026-2027
│   ├── financial-aid-deadlines.md       # FAFSA/CSS Profile info
│   └── nc-homeschool-regulations.md     # NC homeschool laws
│
└── specs/                               # Project documentation
```

---

## 🎯 Who This Guide Is For

### Primary Audience
- **Homeschool families** with students applying to college
- Families in **North Carolina** (but adaptable for any state)
- Students targeting **moderately selective to highly selective universities**
- Families managing **multiple university applications** (guide covers 8 schools)

### Example Use Cases
This guide was designed around 8 specific universities but can be adapted:
- **NC Public Universities**: NC State, UNC Chapel Hill, UNC Charlotte, Appalachian State, NC A&T
- **Private Universities**: Duke
- **Out-of-State Public**: UCLA, Georgia Tech

You can customize by:
- Replacing example universities with your target schools
- Using the research templates to gather requirements for different universities
- Adapting the timeline to your student's grade level and timeline

---

## ✨ Key Features

### 🏠 Homeschool-Specific Focus
Unlike generic college admissions guides, this template addresses unique homeschool challenges:
- ✅ Parent-created transcript templates and examples
- ✅ Letters of recommendation strategies (non-parent recommenders)
- ✅ Third-party validation options (AP, dual enrollment, testing)
- ✅ Homeschool-friendliness ratings for each university
- ✅ NC homeschool law compliance guidance

### 📅 18-Month Timeline
Detailed month-by-month guidance covering:
- **Junior Spring** (Feb-Apr 2026): Planning, SAT prep, campus visits
- **Summer** (May-Aug 2026): Testing, college list finalization, essay writing
- **Senior Fall EA/ED** (Sep-Nov 2026): Final testing, EA/ED applications
- **RD Season** (Dec 2026-Jan 2027): RD applications, financial aid
- **Decision Time** (Feb-Apr 2027): Receive decisions, compare aid packages
- **Enrollment** (May-Aug 2027): Final decision, enrollment, preparation

### 🎓 University Profiles
Each profile includes:
- Admissions requirements and deadlines (EA/ED/RD)
- Test-optional vs. test-required policies
- Middle 50% SAT/ACT ranges and GPA expectations
- Essay requirements and word counts
- Homeschool-specific requirements and friendliness ratings
- Financial aid information and net price calculators
- Program offerings for 7 example career interests
- Application strategy and reach/match/safety assessment

### 📋 Deadline Tracking
16 CSV files ready to import into Google Sheets:
- Organized by university and career interest
- Includes dates, completion status, notes, responsible party
- Master timeline consolidates all deadlines chronologically
- Sortable, filterable, and shareable with family

---

## 🛠️ How to Customize This Guide

### Step 1: Replace Placeholders

Search and replace throughout all files:
- `[Student Name]` → Your student's name
- `[Your Homeschool Name]` → Your homeschool name (e.g., "Smith Family Homeschool")
- `[YEAR]` → Your student's graduation year (e.g., "2027")
- `[Parent Name]` → Parent/administrator name

### Step 2: Adapt to Your Universities

If your target schools differ from the 8 examples:
1. Use the research templates in `research/sources/_RESEARCH_INSTRUCTIONS.md`
2. Follow the same profile structure in `content/guide/03-universities/`
3. Update CSV files in `spreadsheets/` with new deadlines
4. Modify the timeline to reflect different deadline dates

### Step 3: Adjust for Your State

For families outside North Carolina:
- Replace `nc-homeschool-regulations.md` with your state's requirements
- Update in-state status in university profiles
- Research your state's public universities for in-state options
- Verify state-specific financial aid programs

### Step 4: Customize Career Interests

The guide includes 7 example career paths:
- Business, Industrial Design, Architecture, Art, Music Production, Film Production, Aerospace Engineering

Adapt by:
- Replacing career CSV files with your student's interests
- Updating "Programs Offered" section in university profiles
- Researching program-specific requirements (portfolios, auditions, etc.)

---

## 📖 How to Use This Guide

### Monthly Workflow (Recommended)

**Week 1 of Each Month**:
1. Open [`content/guide/02-timeline-overview.md`](content/guide/02-timeline-overview.md)
2. Review the current month's section
3. Read the "Overview" and "Critical Deadlines This Month"
4. Check "Action Items" checklist

**Week 2 of Each Month**:
1. Open your Google Sheets deadline tracker
2. Filter for deadlines in the next 30 days
3. Review university-specific tabs for upcoming tasks

**Week 3 of Each Month**:
1. Work on any applications or prep tasks due next month
2. Update spreadsheet status as tasks are completed

**Week 4 of Each Month**:
1. Review progress on current month's action items
2. Plan ahead for following month's tasks

### Key Documents to Reference

**Before Starting**:
- [`content/guide/04-homeschool-requirements/overview.md`](content/guide/04-homeschool-requirements/overview.md) - Understand homeschool application differences

**During Junior Year**:
- [`research/testing-calendar.md`](research/testing-calendar.md) - SAT/ACT test dates and registration deadlines
- [`content/guide/04-homeschool-requirements/transcripts.md`](content/guide/04-homeschool-requirements/transcripts.md) - Start building transcript

**Summer Before Senior Year**:
- University profiles in [`content/guide/03-universities/`](content/guide/03-universities/) - Finalize college list
- [`content/guide/04-homeschool-requirements/recommendations.md`](content/guide/04-homeschool-requirements/recommendations.md) - Secure recommenders

**Senior Fall**:
- [`spreadsheets/master-timeline.csv`](spreadsheets/master-timeline.csv) - Track all application deadlines
- [`research/financial-aid-deadlines.md`](research/financial-aid-deadlines.md) - FAFSA/CSS Profile timeline

---

## 🎓 Example: North Carolina Resident Applying to 8 Universities

This guide was originally created for a North Carolina homeschool student applying to:

| University | Type | In-State | Test Policy | Acceptance Rate | Why Included |
|------------|------|----------|-------------|-----------------|--------------|
| **NC State** | Public | Yes | Test-optional | 47% | In-state match, strong engineering/design |
| **Duke** | Private | N/A | Test-optional | <5% | In-state reach, highly selective |
| **UCLA** | Public | No | Test-blind | 9% (OOS) | Out-of-state reach, top aerospace/film |
| **App State** | Public | Yes | Test-optional | Moderate | In-state safety, mountain setting |
| **NC A&T** | Public (HBCU) | Yes | Test-optional | 46% | In-state safety, STEM focus |
| **Georgia Tech** | Public | No | Test-required | 9% (OOS) | Out-of-state reach, #2-4 aerospace |
| **UNC Charlotte** | Public | Yes | Test-optional | Moderate | In-state match, architecture program |
| **UNC Chapel Hill** | Public | Yes | Test-optional | 42% (in-state) | In-state match/reach, strong business |

**Example Career Interests**: Business, Industrial Design, Architecture, Art, Music Production, Film Production, Aerospace Engineering

You can use this same structure for your student's unique combination of schools and interests.

---

## 📚 Documentation Structure

### Guide Content (`content/guide/`)
- **README.md**: Main navigation hub (📍 **START HERE**)
- **02-timeline-overview.md**: 18-month timeline with monthly action items
- **03-universities/**: 8 university profiles with complete admissions information
- **04-homeschool-requirements/**: Homeschool-specific guidance and templates

### Research Files (`research/`)
- **sources/**: Detailed admissions requirements research for each university
- **testing-calendar.md**: SAT/ACT dates, deadlines, decision points (2026-2027)
- **financial-aid-deadlines.md**: FAFSA, CSS Profile, scholarship deadlines
- **nc-homeschool-regulations.md**: North Carolina homeschool laws and compliance

### Spreadsheets (`spreadsheets/`)
- **16 CSV files**: University deadlines (8), career deadlines (7), master timeline (1)
- **import-instructions.md**: Step-by-step Google Sheets setup guide

### Project Documentation (`specs/`)
- **spec.md**: Original feature specification
- **plan.md**: Implementation plan and architecture
- **tasks.md**: Task breakdown and phase tracking
- **data-model.md**: Content structure and templates

---

## ✅ Completion Status

**Phases Complete** (5 of 9):
- ✅ **Phase 1**: Project Setup
- ✅ **Phase 2**: Research & Information Gathering (8 universities, testing, financial aid, NC regulations)
- ✅ **Phase 3**: Timeline & Deadline Tracking - MVP (18-month timeline, 16 CSV files)
- ✅ **Phase 4**: University Profiles (8 complete profiles)
- ✅ **Phase 5**: Homeschool Requirements & Templates (60+ pages of guidance)

**Future Phases** (Not Yet Implemented):
- 🔲 **Phase 6**: Career Path Guides (7 comprehensive career guides with day-in-the-life, skills, salary info)
- 🔲 **Phase 7**: Career-University Mapping (8×7 matrix showing which schools offer which programs)
- 🔲 **Phase 8**: Visit Planning (Campus visit guide with checklists and documentation templates)
- 🔲 **Phase 9**: Final Assembly (Introduction, appendices, AI update guide, formatted PDF/DOCX)

The current version provides a **complete, functional MVP** for college admissions planning. Future phases will add additional career exploration and visit planning content.

---

## 🤝 Contributing

This template is designed to be customizable and adaptable. Contributions are welcome:

### How to Contribute
1. **Fork** this repository
2. **Customize** for your needs or add improvements
3. **Submit a pull request** with:
   - Description of changes
   - Rationale for improvements
   - Any new features or content added

### Ideas for Contributions
- Additional university profiles (following the same template structure)
- Career path guides for different fields
- State-specific homeschool regulation guides
- Updated testing calendars for future years
- Scholarship research and deadline tracking
- Application essay guidance and examples
- Financial aid comparison tools

---

## 📄 License

This project is licensed under the MIT License - see below for details.

```
MIT License

Copyright (c) 2026 [Repository Owner]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## ⚠️ Important Disclaimers

### Verify All Information
- **Admissions requirements change annually**: Always verify current deadlines, test policies, and requirements with official university sources
- **Research date**: Information in this guide was verified as of February 2026
- **University websites are authoritative**: Use official admissions pages for final verification

### Not Legal Advice
- This guide provides general information about homeschool requirements
- Consult your state's homeschool regulations and legal resources
- Contact university admissions offices directly with specific questions

### Customization Required
- This is a **template**, not a complete guide ready to use as-is
- **Replace all placeholders** with your student's information
- **Adapt timeline** to your student's grade level and application timeline
- **Research your target universities** using the templates provided

---

## 📞 Getting Help

### For College Admissions Questions
- **University admissions offices**: Contact directly (phone/email in each university profile)
- **FAFSA help**: 1-800-4-FED-AID (1-800-433-3243)
- **Testing**: College Board (SAT) and ACT official websites
- **NC homeschool**: NC Division of Non-Public Education

### For Using This Guide
- **Issues or questions**: Open an issue on GitHub
- **Feature requests**: Submit via GitHub issues
- **General discussion**: Use GitHub discussions

---

## 🌟 Acknowledgments

This guide was created to help homeschool families navigate the complex college admissions process with confidence. It synthesizes best practices from:
- Official university admissions websites and resources
- Homeschool admissions guidance from multiple universities
- College Board and ACT testing information
- Federal Student Aid (FAFSA) resources
- State homeschool regulations and requirements

Special thanks to the homeschool community for sharing experiences and insights that informed this guide's practical, family-tested approach.

---

## 📍 Getting Started

**Ready to begin?** → Start with [`content/guide/README.md`](content/guide/README.md)

This is your main navigation hub. From there, you'll find:
1. The complete guide table of contents
2. Quick start instructions
3. Progress tracking
4. Links to all sections and resources

**Questions?** Open an issue on GitHub or consult the relevant section of the guide.

**Good luck with your college admissions journey!** 🎓

---

**Repository**: https://github.com/shgriffi/university-admission-guide
**Last Updated**: February 14, 2026
**Version**: 1.0 (MVP - Phases 1-5 Complete)
