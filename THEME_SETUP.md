# Academic Theme Setup Guide

## Features

✅ **Light/Dark Mode Toggle** - Enabled in the header
✅ **Minimalistic Design** - Clean, academic aesthetic
✅ **Home Page** - Profile, News, Selected Publications, Latest Blog Posts
✅ **About Page** - Custom layout for biography
✅ **Publications Page** - Lists all papers from the papers section
✅ **Blog Section** - Clean blog listing and posts

## Structure

### Home Page (`layouts/index.html`)
The home page displays:
1. **Profile Section** - Name, photo, bio, social links, navigation buttons
2. **News Section** - Table of recent news items (configurable in `config.yml`)
3. **Selected Publications** - Top publications from papers section
4. **Latest Blog Posts** - Recent blog entries

### Configuration (`config.yml`)

#### Enable Dark Mode Toggle
```yaml
params:
  disableThemeToggle: false  # Set to true to disable
  defaultTheme: light  # Options: light, dark, or auto
```

#### News Section
```yaml
params:
  news:
    enabled: true
    title: "News"
    items:
      - date: "Nov 20, 2023"
        content: "Your news item here"
```

#### Publications Section
```yaml
params:
  publications:
    enabled: true
    title: "Selected Publications"
    limit: 5  # Number of publications to show on home page
```

#### Blog Section
```yaml
params:
  blog:
    enabled: true
    title: "Latest Posts"
    limit: 5  # Number of blog posts to show on home page
```

### Menu Configuration
Update your menu in `config.yml`:
```yaml
menu:
  main:
    - name: About
      url: about/
      weight: 1
    - name: Publications
      url: publications/
      weight: 2
    - name: Blog
      url: blog/
      weight: 3
```

## Content Structure

### About Page
Create `content/about.md`:
```markdown
---
title: "About"
description: "Your description"
---

Your biography here...
```

### Publications Page
The publications page automatically lists all papers from `content/papers/`. Create `content/publications/_index.md`:
```markdown
---
title: "Publications"
description: "All publications"
---
```

### Blog Posts
Create blog posts in `content/blog/`:
```markdown
---
title: "My Blog Post"
date: 2024-01-15
tags: ["tag1", "tag2"]
---

Your blog content...
```

### Mark Papers as Selected
To show specific papers on the home page, add `selected: true` to the front matter:
```yaml
---
title: "Paper Title"
selected: true  # This will appear on home page
---
```

## Customization

### CSS Files
- `assets/css/common/academic-theme.css` - Main theme styles
- `assets/css/common/blog.css` - Blog-specific styles
- `assets/css/common/profile-mode.css` - Profile section styles

### Color Variables
Edit `assets/css/core/theme-vars.css` to customize colors:
- `--primary` - Main text color
- `--secondary` - Secondary text color
- `--darkcolor` - Accent color (links, highlights)
- `--border` - Border colors
- `--theme` - Background color

### Layouts
- `layouts/index.html` - Home page layout
- `layouts/about/single.html` - About page layout
- `layouts/publications/list.html` - Publications listing
- `layouts/blog/list.html` - Blog listing


✅ News table with dates
✅ Publications list with abstracts (expandable)
✅ Author formatting
✅ Venue/journal display
✅ PDF and more links
✅ Blog post listing with dates and tags

## Next Steps

1. **Add News Items** - Edit `config.yml` to add your news items
2. **Mark Selected Papers** - Add `selected: true` to papers you want on the home page
3. **Create Blog Posts** - Add posts to `content/blog/`
4. **Customize Colors** - Edit theme variables in `theme-vars.css`
5. **Update Profile** - Edit profile settings in `config.yml` under `profileMode`

## Testing

Run your Hugo site:
```bash
hugo server
```

Visit:
- Home page: `http://localhost:1313/`
- About: `http://localhost:1313/about/`
- Publications: `http://localhost:1313/publications/`
- Blog: `http://localhost:1313/blog/`

Toggle dark mode using the button in the header!

