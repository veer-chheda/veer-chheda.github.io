# Theme Customization Guide

This guide explains how to customize the look of specific pages in your Hugo site using the PaperMod theme.

## How Hugo Theme Customization Works

In Hugo, files in your site directory **override** files in the theme directory. The hierarchy is:
1. **Site layouts** (`pages/layouts/`) - Your customizations (highest priority)
2. **Theme layouts** (`pages/themes/PaperMod/layouts/`) - Default theme files

## Current Customization Structure

You already have:
- **Custom CSS**: `pages/assets/css/` - These override theme CSS
- **Custom Layouts**: `pages/layouts/` - These override theme layouts

## Ways to Customize Pages

### 1. Customize CSS for Specific Pages

You can add page-specific CSS classes and styles:

**Option A: Add CSS to existing files**
- Edit files in `pages/assets/css/common/` (e.g., `post-entry.css`, `post-single.css`)
- These styles apply globally

**Option B: Create page-specific CSS**
- Create new CSS files in `pages/assets/css/`
- Reference them in layouts using conditional logic

### 2. Customize the Home Page

The home page uses `layouts/_default/list.html` when `.IsHome` is true.

**To customize the home page specifically:**
- Create `layouts/index.html` - This will override the default list template for the home page
- Or modify `layouts/_default/list.html` and add conditions like `{{- if .IsHome }}`

### 3. Customize Section Pages (e.g., Papers, Books, Courses)

**To customize the papers section specifically:**
- Create `layouts/papers/list.html` - This will be used for the papers listing page
- Create `layouts/papers/single.html` - This will be used for individual paper pages

**To customize the books section:**
- Create `layouts/books/list.html`
- Create `layouts/books/single.html`

### 4. Customize Individual Page Types

You can also customize based on content type or front matter:
- Add a `layout` parameter in the page's front matter
- Create a corresponding layout file

## Examples

### Example 1: Custom Papers List Page

Create `layouts/papers/list.html`:
```html
{{- define "main" }}
<header class="page-header">
  <h1>Research Papers</h1>
  <p class="custom-papers-intro">Browse my published research...</p>
</header>

{{- range .Pages }}
<article class="paper-entry">
  <h2>{{ .Title }}</h2>
  <!-- Custom paper listing layout -->
</article>
{{- end }}
{{- end }}
```

### Example 2: Add Custom CSS for Papers Section

Create `pages/assets/css/common/papers.css`:
```css
.papers-section {
    background: var(--code-bg);
    padding: var(--gap);
}

.paper-entry {
    /* Custom styles for paper entries */
}
```

Then reference it in `layouts/partials/head.html` or add it conditionally.

### Example 3: Customize Home Page Layout

Create `layouts/index.html`:
```html
{{- define "main" }}
<div class="custom-home">
  <h1>Welcome</h1>
  <!-- Your custom home page content -->
</div>
{{- end }}
```

## File Structure Reference

```
pages/
├── layouts/
│   ├── _default/          # Default templates (used when no specific template exists)
│   │   ├── list.html      # For listing pages (home, sections)
│   │   ├── single.html    # For individual pages
│   │   └── baseof.html    # Base template
│   ├── papers/            # Papers-specific templates
│   │   ├── list.html      # Papers listing page
│   │   └── single.html    # Individual paper page
│   ├── books/             # Books-specific templates
│   │   └── ...
│   └── partials/          # Reusable components
│       ├── header.html
│       └── footer.html
├── assets/
│   └── css/
│       ├── common/        # Global CSS files
│       └── core/          # Core variables
└── themes/
    └── PaperMod/          # Theme files (don't edit directly)
```

## Tips

1. **Don't edit theme files directly** - Always override in `pages/layouts/` or `pages/assets/`
2. **Use CSS variables** - Defined in `theme-vars.css`, use `var(--variable-name)`
3. **Test incrementally** - Make small changes and test
4. **Check Hugo docs** - For template syntax and functions

## Quick Reference: Template Lookup Order

Hugo looks for templates in this order:
1. `layouts/{Section}/{Type}.html` (e.g., `layouts/papers/list.html`)
2. `layouts/{Section}/single.html` (e.g., `layouts/papers/single.html`)
3. `layouts/_default/{Type}.html` (e.g., `layouts/_default/list.html`)
4. Theme templates

