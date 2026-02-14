# Quickstart Guide: GitHub Pages Website

**Feature**: GitHub Pages Website with Navigation
**Date**: 2026-02-14
**Purpose**: Complete guide for setting up GitHub Pages (no Ruby/Bundler required!)

---

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Adding Front Matter to Content Files](#adding-front-matter-to-content-files)
3. [Converting Internal Links](#converting-internal-links)
4. [Deploying to GitHub Pages](#deploying-to-github-pages)
5. [Testing Your Site](#testing-your-site)
6. [Troubleshooting](#troubleshooting)
7. [Validation Checklist](#validation-checklist)
8. [Optional: Local Testing](#optional-local-testing)

---

## Prerequisites

### Required

- **Git** (for version control and deployment)
- **GitHub account** with repository access
- **Text editor** (VS Code, Sublime, Notepad++, etc.)

### NOT Required

- ❌ Ruby installation
- ❌ Bundler
- ❌ Jekyll installation
- ❌ Local web server

**Why?** GitHub Pages automatically builds Jekyll sites on their servers. You just push your markdown files and configuration, and GitHub handles the rest!

---

## Quick Start Overview

The basic workflow is:

1. **Add front matter** to all markdown files (defines navigation)
2. **Convert internal links** to root-relative paths
3. **Push to GitHub** (main branch)
4. **Enable GitHub Pages** in repository settings
5. **Visit your live site!** GitHub builds it automatically

That's it! No local setup required.

---

## Adding Front Matter to Content Files

**Status**: Front matter has been added to **2 of 60+ files**. The remaining files need front matter added.

### What is Front Matter?

Front matter is YAML metadata at the very beginning of each markdown file that tells Jekyll how to render the page and where it appears in navigation.

### Front Matter Template

Every content markdown file needs YAML front matter at the very beginning:

```yaml
---
layout: page
title: "Display Name"
nav_order: 1
parent: "Parent Page Title"  # Optional, for 2nd level pages
---
```

**Important**: Front matter must be:
- The very first thing in the file (before any markdown content)
- Enclosed in triple dashes (`---`)
- Valid YAML syntax (proper indentation, quotes around strings with special characters)

### Files Needing Front Matter

#### ✅ Already Completed

- `/README.md` (Home page)
- `/content/guide/02-timeline-overview.md` (Timeline)

#### ⏭️ Step 1: Create Section Landing Pages

Create these new files to serve as navigation parents:

**`/content/guide/03-universities/README.md`**:
```markdown
---
layout: page
title: "Universities"
nav_order: 3
has_children: true
---

# University Profiles

Detailed admissions information for 8 target universities.

## Included Universities

- [NC State](nc-state)
- [Duke](duke)
- [UCLA](ucla)
- [Appalachian State](appalachian-state)
- [NC A&T](nc-at)
- [Georgia Tech](georgia-tech)
- [UNC Charlotte](unc-charlotte)
- [UNC Chapel Hill](unc-chapel-hill)
```

**`/content/guide/04-homeschool-requirements/README.md`**:
```markdown
---
layout: page
title: "Homeschool Requirements"
nav_order: 4
has_children: true
---

# Homeschool-Specific Requirements

Complete guidance for homeschool students applying to college.

## Topics Covered

- Overview of homeschool admissions
- Transcript preparation
- Letters of recommendation
- Third-party validation
- NC homeschool regulations
- Templates and samples
```

**`/research/README.md`**:
```markdown
---
layout: page
title: "Research"
nav_order: 5
has_children: true
---

# Research and References

Testing calendars, financial aid information, and state regulations.

## Available Resources

- SAT/ACT testing calendar (2026-2027)
- Financial aid deadlines (FAFSA, CSS Profile)
- NC homeschool regulations
```

#### ⏭️ Step 2: Add Front Matter to Universities (8 files)

For each university file in `content/guide/03-universities/`, add front matter:

**Pattern**:
```yaml
---
layout: page
title: "[University Name]"
parent: "Universities"
nav_order: [1-8]
---
```

**Example** (`content/guide/03-universities/nc-state.md`):
```yaml
---
layout: page
title: "NC State"
parent: "Universities"
nav_order: 1
---

# North Carolina State University
[rest of existing content...]
```

**All 8 Files**:
1. `nc-state.md` (nav_order: 1)
2. `duke.md` (nav_order: 2)
3. `ucla.md` (nav_order: 3)
4. `appalachian-state.md` (nav_order: 4)
5. `nc-at.md` (nav_order: 5)
6. `georgia-tech.md` (nav_order: 6)
7. `unc-charlotte.md` (nav_order: 7)
8. `unc-chapel-hill.md` (nav_order: 8)

#### ⏭️ Step 3: Add Front Matter to Homeschool Requirements (8 files)

For each file in `content/guide/04-homeschool-requirements/`, add front matter:

**Pattern**:
```yaml
---
layout: page
title: "[Topic Name]"
parent: "Homeschool Requirements"
nav_order: [1-8]
---
```

**All 8 Files**:
1. `overview.md` (nav_order: 1)
2. `transcripts.md` (nav_order: 2)
3. `recommendations.md` (nav_order: 3)
4. `validation.md` (nav_order: 4)
5. `nc-regulations.md` (nav_order: 5)
6. `transcript-template.md` (nav_order: 6)
7. `transcript-sample.md` (nav_order: 7)
8. `google-docs-instructions.md` (nav_order: 8)

#### ⏭️ Step 4: Add Front Matter to Research (3 files)

For each file in `research/`, add front matter:

**All 3 Files**:
1. `testing-calendar.md`:
   ```yaml
   ---
   layout: page
   title: "Testing Calendar"
   parent: "Research"
   nav_order: 1
   ---
   ```

2. `financial-aid-deadlines.md`:
   ```yaml
   ---
   layout: page
   title: "Financial Aid Deadlines"
   parent: "Research"
   nav_order: 2
   ---
   ```

3. `nc-homeschool-regulations.md`:
   ```yaml
   ---
   layout: page
   title: "NC Homeschool Regulations"
   parent: "Research"
   nav_order: 3
   ---
   ```

#### ⏭️ Step 5: Add Front Matter to Spreadsheets

**`spreadsheets/import-instructions.md`**:
```yaml
---
layout: page
title: "Spreadsheets"
nav_order: 6
---
```

---

## Converting Internal Links

**Status**: Link conversion not yet started.

### Why Convert Links?

Jekyll on GitHub Pages needs links in a specific format to work correctly. All internal links must be:
- **Root-relative**: Start with `/`
- **Without file extensions**: Remove `.md` from links

### Current vs. Target Format

**Before** (relative paths with .md):
```markdown
See the [NC State profile](./03-universities/nc-state.md) for details.
Check [timeline overview](../02-timeline-overview.md) first.
```

**After** (root-relative, no .md):
```markdown
See the [NC State profile](/content/guide/03-universities/nc-state) for details.
Check [timeline overview](/content/guide/02-timeline-overview) first.
```

### Manual Conversion Process

For each markdown file:

1. **Open the file** in your text editor
2. **Find links**: Use Find (Ctrl+F / Cmd+F) to search for `](`
3. **Convert each link**:
   - Relative `./` → Root-relative `/content/guide/`
   - Relative `../` → Adjust to appropriate root path
   - Remove `.md` extension from all internal links
4. **Save the file**

### Common Link Patterns

| Current Link | Converted Link |
|--------------|----------------|
| `[Link](./file.md)` | `[Link](/content/guide/file)` |
| `[Link](../file.md)` | `[Link](/content/file)` |
| `[Link](file.md)` | `[Link](/content/guide/file)` |
| `[CSV](../spreadsheets/file.csv)` | `[CSV](/spreadsheets/file.csv)` |

**Leave unchanged**:
- External links: `https://example.com`
- CSV files: Keep `.csv` extension
- Anchor links: `#section-name`

### External Links (Add New Tab Behavior)

For external links to open in new tabs, add `{:target="_blank"}` after the link:

**Before**:
```markdown
[University Website](https://example.com)
```

**After**:
```markdown
[University Website](https://example.com){:target="_blank"}
```

This uses kramdown syntax (Jekyll's markdown processor) to add `target="_blank"` automatically.

---

## Deploying to GitHub Pages

### Step 1: Commit Your Changes

```bash
# Navigate to repository
cd /home/shgriffi/dev/college/connor

# Check what files changed
git status

# Add all modified files
git add .

# Commit with descriptive message
git commit -m "Add Jekyll configuration and front matter for GitHub Pages"

# Push to main branch
git push origin main
```

### Step 2: Enable GitHub Pages

1. **Go to your repository** on GitHub: `https://github.com/shgriffi/university-admission-guide`
2. Click the **Settings** tab
3. Scroll down to **Pages** in the left sidebar
4. Under **Source**:
   - **Branch**: Select `main`
   - **Folder**: Select `/ (root)`
   - Click **Save**

### Step 3: Wait for Build (1-3 minutes)

1. Go to **Actions** tab in your repository
2. You'll see a workflow called "pages build and deployment"
3. Click on it to watch the build progress
4. Wait for green checkmark ✅ (build succeeded)

### Step 4: Visit Your Live Site!

Once the build completes (green checkmark), your site is live at:

**https://shgriffi.github.io/university-admission-guide/**

---

## Testing Your Site

### Post-Deployment Testing

After GitHub Pages builds your site, test these areas:

#### Homepage Test
- [ ] Visit `https://shgriffi.github.io/university-admission-guide/`
- [ ] Page loads without errors
- [ ] Title and content display correctly
- [ ] Navigation menu appears on left sidebar

#### Navigation Test
- [ ] Click "Universities" in sidebar → expands to show 8 schools
- [ ] Click "NC State" → navigates to NC State page
- [ ] Current page is highlighted in navigation
- [ ] Click "Homeschool Requirements" → expands to show all subsections
- [ ] All menu items are clickable and navigate correctly

#### Mobile Navigation Test (resize browser or use phone)
- [ ] Hamburger menu icon appears on small screens (<768px)
- [ ] Click hamburger → navigation opens
- [ ] Navigation is scrollable and usable
- [ ] Click a link → navigates and closes menu

#### Link Testing
- [ ] Click internal links from various pages
- [ ] Verify no 404 errors on internal links
- [ ] Click external links → open in new tabs
- [ ] Click CSV links → files download

#### Responsive Design Test

Test at these screen widths (use browser DevTools):
- [ ] 320px (Mobile - iPhone SE)
- [ ] 768px (Tablet - iPad)
- [ ] 1920px (Desktop)

Verify content is readable and navigation works at all sizes.

---

## Troubleshooting

### Build Failed in Actions Tab

**Symptom**: Red X on "pages build and deployment" workflow

**Solutions**:
1. Click on the failed workflow to see error message
2. Common issues:
   - **YAML syntax error**: Check front matter has proper indentation and closing `---`
   - **Invalid configuration**: Verify `_config.yml` syntax
   - **Missing files**: Ensure all referenced files exist

### Navigation Menu Not Showing

**Possible Causes**:
- Missing front matter in files
- Incorrect `parent` field (doesn't match parent page title exactly)
- Missing section landing pages (README.md files)

**Solution**:
- Verify all pages have `title`, `nav_order`, and (if applicable) `parent` in front matter
- Check that parent names match exactly (case-sensitive)
- Create landing pages for Universities, Homeschool Requirements, Research

### Internal Links Leading to 404

**Causes**:
- Links still have `.md` extension
- Links use relative paths instead of root-relative
- File doesn't exist at specified path

**Solutions**:
- Remove `.md` from all internal links
- Convert to root-relative: `/content/guide/file` not `./file`
- Verify file exists at the path specified in link

### Changes Not Appearing on Live Site

**Cause**: GitHub Pages caching

**Solutions**:
- Wait 1-2 minutes for build to complete
- Hard refresh browser: Ctrl+Shift+R (Windows/Linux) or Cmd+Shift+R (Mac)
- Check Actions tab to confirm build succeeded
- Try incognito/private browsing window

### Theme Not Loading Correctly

**Cause**: `remote_theme` configuration issue

**Solution**:
- Verify `_config.yml` has `remote_theme: just-the-docs/just-the-docs`
- NOT `theme: just-the-docs` (that's for local only)
- Push changes and wait for rebuild

---

## Validation Checklist

### Pre-Deployment Validation

Before pushing to GitHub:

- [ ] All content files have front matter added
- [ ] Section landing pages created (Universities, Homeschool Requirements, Research)
- [ ] All internal links converted to root-relative format
- [ ] All `.md` extensions removed from internal links
- [ ] External links have `{:target="_blank"}` added
- [ ] Changes committed to Git

### Post-Deployment Validation

After GitHub Pages deployment:

- [ ] Site URL accessible: `https://shgriffi.github.io/university-admission-guide/`
- [ ] Homepage displays correctly
- [ ] Navigation menu shows all sections
- [ ] All pages accessible from menu
- [ ] Internal links work (no 404s)
- [ ] External links open in new tabs
- [ ] Mobile responsive (test on phone or resize browser)

### Success Criteria Validation

Verify all original success criteria:

- [ ] **SC-001**: Navigate to any section in ≤3 clicks
- [ ] **SC-002**: 100% internal links work without 404s
- [ ] **SC-003**: Homepage loads in <3 seconds
- [ ] **SC-004**: Navigation usable on 320px - 1920px screens
- [ ] **SC-005**: All 8 universities accessible in ≤2 clicks
- [ ] **SC-006**: 100% external links open in new tabs
- [ ] **SC-007**: Website deploys to GitHub Pages with zero errors
- [ ] **SC-008**: All CSVs downloadable in 1 click

---

## Optional: Local Testing

**Note**: Local testing is completely optional! GitHub Pages will build your site automatically. However, if you want to preview changes before pushing, you can set up local Jekyll.

### Install Ruby and Bundler

Choose your operating system:

#### Windows 11 (Command Line)

**Step 1: Install Ruby using RubyInstaller**

1. **Download RubyInstaller**:
   - Visit: https://rubyinstaller.org/downloads/
   - Download: **Ruby+Devkit 3.2.X (x64)** - recommended version with development tools
   - File will be named something like: `rubyinstaller-devkit-3.2.X-1-x64.exe`

2. **Run the installer**:
   - Double-click the downloaded `.exe` file
   - Check **"Add Ruby executables to your PATH"** (important!)
   - Check **"Associate .rb and .rbw files with this Ruby installation"**
   - Click **Install**
   - When prompted, select **"Run 'ridk install'"** to setup MSYS2
   - In the command window that appears, press **Enter** to run default installation (option 3)
   - Wait for MSYS2 installation to complete

3. **Verify Ruby installation**:
   - Open a **new Command Prompt** (Start → type `cmd` → Enter)
   - Or open **PowerShell** (Start → type `powershell` → Enter)
   - Run:
     ```cmd
     ruby --version
     ```
   - You should see: `ruby 3.2.x`

4. **Install Bundler**:
   ```cmd
   gem install bundler
   ```

5. **Verify Bundler installation**:
   ```cmd
   bundler --version
   ```
   - You should see: `Bundler version 2.x.x`

**Step 2: Install Jekyll Dependencies**

1. **Navigate to your project** (use Command Prompt or PowerShell):
   ```cmd
   cd C:\path\to\your\college\connor
   ```

2. **Install all gems**:
   ```cmd
   bundle install
   ```
   - This will install Jekyll, GitHub Pages gem, Just-the-Docs theme, and all plugins
   - Installation takes 2-5 minutes

**Step 3: Run Local Server**

```cmd
bundle exec jekyll serve
```

**Step 4: View in Browser**

- Open your browser
- Go to: **http://localhost:4000/**
- Site will auto-refresh when you edit files!

**Common Windows Issues & Solutions**:

**Issue**: "Jekyll command not found"
- **Solution**: Use `bundle exec jekyll serve` instead of just `jekyll serve`

**Issue**: "Could not find gem 'wdm'"
- **Solution**: Run `bundle install` again

**Issue**: "SSL certificate problem"
- **Solution**: Update SSL certificates:
  ```cmd
  gem update --system
  ```

**Issue**: Port 4000 already in use
- **Solution**: Use a different port:
  ```cmd
  bundle exec jekyll serve --port 4001
  ```
  - Then visit: http://localhost:4001/

**Stopping the server**:
- Press `Ctrl + C` in the command prompt/PowerShell window

---

#### WSL2/Ubuntu (Windows Subsystem for Linux)

If you're using WSL2 instead of native Windows:

```bash
# Update package lists
sudo apt update

# Install Ruby and build dependencies
sudo apt install ruby-full build-essential zlib1g-dev -y

# Configure gem installation directory
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# Install Bundler
gem install bundler

# Verify installation
ruby --version
bundler --version

# Navigate to project and install dependencies
cd /home/shgriffi/dev/college/connor
bundle install

# Start server
bundle exec jekyll serve
```

Visit: **http://localhost:4000/**

---

#### macOS

```bash
# Install Homebrew (if not installed)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Ruby
brew install ruby

# Add to PATH
echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

# Install Bundler
gem install bundler

# Navigate to project and install dependencies
cd /path/to/college/connor
bundle install

# Start server
bundle exec jekyll serve
```

Visit: **http://localhost:4000/**

---

#### Fedora/RHEL/CentOS

For Fedora, Red Hat Enterprise Linux, or CentOS:

```bash
# Update package lists
sudo dnf update -y

# Install Ruby and all build dependencies
sudo dnf install ruby ruby-devel gcc gcc-c++ make redhat-rpm-config zlib-devel openssl-devel git -y

# Configure gem installation directory (avoid needing sudo for gems)
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# Install Bundler
gem install bundler

# Verify installation
ruby --version
bundler --version

# Navigate to project and install dependencies
cd /path/to/college/connor
bundle install

# Start server
bundle exec jekyll serve
```

Visit: **http://localhost:4000/**

**Fedora-Specific Notes**:
- Fedora typically comes with a recent Ruby version (3.x+)
- If you need a specific Ruby version, consider using [rbenv](https://github.com/rbenv/rbenv) or [RVM](https://rvm.io/)
- SELinux may affect file permissions - if you encounter permission errors, check SELinux status with `getenforce`

---

### Local Testing Workflow

Once Jekyll is running locally:

1. **Edit files** in your text editor (VS Code, Notepad++, etc.)
2. **Save changes**
3. **Refresh browser** - changes appear automatically!
4. **No need to restart server** - it watches for file changes

### What You Can Test Locally

- ✅ Front matter changes (navigation)
- ✅ Internal link conversions
- ✅ Markdown content rendering
- ✅ Layout and styling
- ✅ Responsive design (resize browser)
- ✅ Navigation menu functionality

### When to Use Local Testing

**Use local testing when**:
- Making lots of changes and want quick feedback
- Experimenting with layout/style changes
- Debugging navigation or link issues
- Want to catch YAML errors before pushing

**Skip local testing when**:
- Making simple content updates (front matter, text edits)
- Just want to see final result on GitHub Pages
- Don't want to install Ruby/Bundler (just push to GitHub instead)

### Useful Jekyll Commands

```cmd
# Clean build cache (if you have issues)
bundle exec jekyll clean

# Build site without serving (just generate _site folder)
bundle exec jekyll build

# Serve with live reload (auto-refresh browser)
bundle exec jekyll serve --livereload

# Serve on different port
bundle exec jekyll serve --port 4001

# Verbose output (for debugging)
bundle exec jekyll serve --verbose
```

**Recommendation**: Local testing is great for quick iteration, but GitHub Pages deployment is the simplest option if you're just getting started!

---

## Next Steps After Deployment

1. **Share the URL** with family/friends for feedback
2. **Update README** at repository root with live site link
3. **Monitor builds**: Check Actions tab after each push
4. **Add custom domain** (optional): Configure in Settings → Pages
5. **Enable Google Analytics** (optional): Add tracking code

---

## Summary of Required Steps

1. ✅ Configuration files created (_config.yml, Gemfile)
2. ⏭️ Add front matter to ~60 markdown files
3. ⏭️ Create 3 section landing pages (README.md files)
4. ⏭️ Convert internal links to root-relative format
5. ⏭️ Commit and push to GitHub
6. ⏭️ Enable GitHub Pages in repository settings
7. ⏭️ Test live site

**Estimated Time**: 1-2 hours for front matter and link conversion

**No Ruby/Bundler required** - GitHub Pages handles all Jekyll processing automatically!

---

**File Location**: `/home/shgriffi/dev/college/connor/specs/003-github-pages-site/quickstart.md`
**Last Updated**: 2026-02-14
**Related Files**:
- [Feature Specification](spec.md)
- [Implementation Plan](plan.md)
- [Data Model](data-model.md)
- [Research](research.md)
- [Tasks](tasks.md)
