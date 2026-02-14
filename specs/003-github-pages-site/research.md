# Research: GitHub Pages Website Implementation

**Feature**: GitHub Pages Website with Navigation
**Date**: 2026-02-14
**Purpose**: Document technical decisions for Jekyll theme, navigation, deployment, and link migration

---

## 1. Jekyll Theme Decision

**Decision**: **Just-the-Docs**

**Rationale**:
- **Built-in navigation support**: Automatic generation of hierarchical navigation from YAML data
- **Mobile responsive**: Includes hamburger menu pattern for mobile devices (<768px)
- **Documentation-focused**: Specifically designed for documentation sites, perfect for our college guide
- **GitHub Pages compatible**: Available as remote theme via github-pages gem
- **Minimal customization needed**: Provides all required features out-of-the-box
- **Active page indication**: Built-in highlighting of current page in navigation
- **Search functionality**: Includes search feature (bonus for future enhancement)
- **Clean, professional design**: Matches the professional appearance requirement

**Alternatives Considered**:

1. **Minimal Architect**:
   - Pros: Clean minimal design, GitHub Pages compatible
   - Cons: Limited navigation features, would require more custom code

2. **Minimal Mistakes**:
   - Pros: Feature-rich, highly customizable, excellent navigation
   - Cons: May be overkill for our needs, more complex setup

3. **Cayman**:
   - Pros: Simple and clean, GitHub Pages default
   - Cons: No built-in navigation menu, would require significant custom development

4. **Minima**:
   - Pros: Default Jekyll theme, very lightweight
   - Cons: Minimal navigation support, requires extensive customization

**Installation**:

Add to `_config.yml`:
```yaml
remote_theme: just-the-docs/just-the-docs
```

Add to `Gemfile` (if using locally):
```ruby
gem "just-the-docs"
```

**Configuration**: Just-the-Docs uses `_config.yml` for site-wide settings and front matter in pages for individual page configuration.

---

## 2. Navigation Structure

**Decision**: Use Just-the-Docs' built-in navigation system with `_data/navigation.yml` and page front matter

**Rationale**:
- **Separation of concerns**: Navigation structure in YAML keeps it separate from content
- **Hierarchical support**: Just-the-Docs natively supports multi-level navigation
- **Maintainable**: Easy to add/remove/reorganize navigation items
- **Dynamic**: Can use Liquid templating for active page indication

**Pattern**: Hierarchical nested structure using page front matter

**Configuration Approach**:
1. Set `nav_order` in each page's front matter to control position
2. Use `parent` and `grand_parent` for hierarchical relationships
3. Set `has_children: true` for pages with subpages

**Example Front Matter**:
```yaml
---
title: Universities
nav_order: 3
has_children: true
---
```

```yaml
---
title: NC State
parent: Universities
nav_order: 1
---
```

**Mobile Implementation**: Just-the-Docs provides CSS-only hamburger menu that:
- Collapses navigation on screens <768px
- Expands on tap/click
- No JavaScript required (graceful degradation)
- Accessible via keyboard navigation

**Active Page Indication**: Just-the-Docs automatically highlights the current page and its ancestors in the navigation tree using CSS classes.

---

## 3. Deployment Configuration

**Decision**: Deploy from **main branch, root directory**

**Configuration Steps**:

1. **Enable GitHub Pages**:
   - Go to repository Settings → Pages
   - Source: Deploy from a branch
   - Branch: main
   - Folder: / (root)
   - Save

2. **Configure `_config.yml`**:
   ```yaml
   baseurl: "" # Empty for root deployment
   url: "https://[username].github.io" # Will be auto-set by GitHub Pages
   ```

3. **Push changes to main branch**:
   - GitHub Pages automatically builds when changes are pushed
   - Build status visible in Actions tab

**Validation**:
- Check Actions tab for build success/failure
- Visit `https://[username].github.io/[repo-name]` once build completes
- Verify site loads without errors

**Benefits of Main Branch Deployment**:
- Single-branch workflow (no separate gh-pages branch)
- Simpler git history
- Modern GitHub Pages default approach
- Automatic builds on every push to main

---

## 4. Link Standardization

**Current State**:
After auditing existing markdown files, current link formats include:
- Relative paths: `./nc-state.md`, `../timeline-overview.md`
- Markdown-specific links: `[Link](file.md)`
- Some root-relative paths: `/content/guide/universities/nc-state.md`

**Target State**:
All internal links should use **root-relative paths** starting with `/`:
- Format: `/content/guide/universities/nc-state` (without `.md` or `.html`)
- Jekyll will automatically append `.html` during build
- Works in both repository view (GitHub) and GitHub Pages

**Migration Approach**:

**Manual Find/Replace**:
1. Use editor's find/replace for each directory
2. Pattern: `](./` → `](/content/guide/...`
3. Pattern: `](../` → `](/content/...` (adjust path accordingly)
4. Remove `.md` extensions from links

**Automation Script** (bash):
```bash
# Find all markdown files and convert relative links to root-relative
find content/ research/ spreadsheets/ README.md -name "*.md" -type f -exec sed -i 's|](./|](/content/guide/|g' {} +
find content/ research/ spreadsheets/ README.md -name "*.md" -type f -exec sed -i 's|](../|](/content/|g' {} +
# Remove .md extensions
find content/ research/ spreadsheets/ README.md -name "*.md" -type f -exec sed -i 's|\.md)|)|g' {} +
```

**Jekyll URL Handling**:
- Jekyll's `permalink: pretty` setting removes `.html` from URLs
- Internal links work as: `/content/guide/timeline-overview`
- Jekyll serves as: `https://site.com/content/guide/timeline-overview/`
- Markdown `.md` files become `.html` in build output

**Testing**:
1. **Local testing**: `bundle exec jekyll serve` and click all links
2. **HTML Proofer gem**:
   ```ruby
   gem "html-proofer"
   ```
   Run: `htmlproofer ./_site --disable-external`
3. **Manual verification**: After deployment, test all pages systematically

**Link Types to Convert**:
- ✅ Internal content links: `/content/guide/...`
- ✅ Research links: `/research/...`
- ✅ Spreadsheet links: `/spreadsheets/...`
- ✅ Homepage link: `/`
- ⚠️ CSV downloads: Keep as-is, Jekyll serves raw files
- ⚠️ External links: Leave unchanged, add `target="_blank"`

**External Link Handling**:
Use Jekyll plugin or JavaScript to add `target="_blank"` to external links:

**Option 1: kramdown attribute** (add to each external link):
```markdown
[University Website](https://example.com){:target="_blank"}
```

**Option 2: JavaScript** (automatic):
```javascript
document.querySelectorAll('a[href^="http"]').forEach(link => {
  if (!link.href.includes(window.location.hostname)) {
    link.target = '_blank';
    link.rel = 'noopener noreferrer';
  }
});
```

---

## 5. Additional Technical Decisions

### Performance Optimization

**CSS/JS Minification**: Just-the-Docs includes optimized assets
**Image Optimization**: No images in current guide (primarily text/markdown)
**Caching**: GitHub Pages sets appropriate cache headers automatically

### Browser Compatibility

**Target Browsers**: Chrome, Firefox, Safari, Edge (last 2 years)
**Responsive Breakpoints**:
- Mobile: 320px - 767px (hamburger menu)
- Tablet: 768px - 1023px (partial navigation)
- Desktop: 1024px+ (full navigation)

### Accessibility

**Just-the-Docs Accessibility Features**:
- Semantic HTML structure
- ARIA labels for navigation
- Keyboard navigation support
- High contrast color scheme
- Scalable text (relative units)

---

## Next Steps

1. ✅ Theme selected: Just-the-Docs
2. ⏭️ Update `_config.yml` with theme configuration
3. ⏭️ Update `Gemfile` with theme gem
4. ⏭️ Add front matter to all content pages for navigation
5. ⏭️ Convert all internal links to root-relative paths
6. ⏭️ Test locally with `bundle exec jekyll serve`
7. ⏭️ Deploy to GitHub Pages and validate

---

**File Location**: `/home/shgriffi/dev/college/connor/specs/003-github-pages-site/research.md`
**Related Files**:
- [Feature Specification](spec.md)
- [Implementation Plan](plan.md)
- [Task List](tasks.md)
