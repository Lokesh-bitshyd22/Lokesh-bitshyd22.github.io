# Portfolio — Jekyll Site

Minimalist personal site with blog. Built with Jekyll, hosted on GitHub Pages.

## Quick Start

### 1. Prerequisites

Install Ruby and Bundler:
```bash
# macOS
brew install ruby
gem install bundler

# Ubuntu/Debian
sudo apt install ruby-full
gem install bundler
```

### 2. Install dependencies

```bash
cd portfolio
bundle install
```

### 3. Run locally

```bash
bundle exec jekyll serve
# Open http://localhost:4000
```

---

## Deploy to GitHub Pages

### Step 1 — Create the repo

Go to github.com → New repository → name it exactly:
```
your-github-username.github.io
```
(e.g. `lokesh2005.github.io`)

### Step 2 — Push the site

```bash
git init
git add .
git commit -m "initial site"
git branch -M main
git remote add origin https://github.com/lokesh2005/lokesh2005.github.io.git
git push -u origin main
```

### Step 3 — Enable Pages

GitHub repo → Settings → Pages → Source: Deploy from branch → Branch: main / (root)

Your site goes live at `https://lokesh2005.github.io` within a minute or two.

---

## Customization Guide

### Personal details — `_config.yml`

```yaml
title: Lokesh                          # Your name
description: Developer. Builder.       # One-liner shown in browser tab
email: your@email.com                  # Contact email
url: https://lokesh2005.github.io      # Your GitHub Pages URL
github_username: lokesh2005
linkedin_username: lokesh2005
```

### Home page — `index.md`

Edit the intro blurb, "Now" section, and featured projects.

### About page — `about.md`

Fill in:
- Short bio paragraphs
- Skills grid (languages, tools, interests, learning)
- Experience / education entries

### Projects page — `projects.md`

Copy-paste the `project-item` block for each project. Fill in:
- Project name and description
- Tags (tech stack)
- GitHub link and year

### Writing / Blog — `_posts/`

Create a new file for each post:

**Filename format:** `YYYY-MM-DD-post-title.md`

**File front matter:**
```yaml
---
layout: post
title: "Your Post Title"
date: 2025-06-01
tags: [learning, projects]
---

Your content here in Markdown.
```

---

## File Structure

```
portfolio/
├── _config.yml          ← site settings
├── _layouts/
│   ├── default.html     ← header/footer shell
│   └── post.html        ← blog post template
├── _posts/
│   └── YYYY-MM-DD-*.md  ← your blog posts
├── assets/css/
│   └── main.css         ← all styles
├── index.md             ← home page
├── about.md             ← about page
├── projects.md          ← projects page
├── blog.md              ← blog index
└── Gemfile
```

---

## Tips

- Update the "Now" section on `index.md` every month or so — keeps the site feeling alive.
- Keep posts short. 300–600 words beats 2000-word tutorials that never get written.
- Don't overthink the design. The minimalism is the point.
