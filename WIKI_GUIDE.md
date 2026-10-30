# Product Wiki & Blog Management Guide

This guide explains how to maintain, extend, and customize this repository as a personal wiki site for product documentation and blogs hosted on **GitHub Pages**.

---

## 🏗️ Repository Architecture

```text
├── _config.yml         # Jekyll configuration (theme, title, plugins, permalinks)
├── index.md            # Home portal page linking to docs and blog
├── WIKI_GUIDE.md       # This guide
├── docs/               # Product Documentation Hub
│   ├── index.md        # Docs hub index page
│   └── <product>/      # Product-specific folders (e.g., docs/insightpage/)
├── blog/
│   └── index.md        # Blog list page
├── _posts/             # Jekyll Blog posts (YYYY-MM-DD-title.md)
└── README.md           # Repository overview
```

---

## 📝 How to Add Product Documentation

1. Create a folder under `docs/` named after your product (e.g. `docs/my-product/`).
2. Add your Markdown documentation pages, using Front Matter at the top:
   ```markdown
   ---
   layout: page
   title: My Product - Getting Started
   parent: Documentation Hub
   ---
   # My Product
   Your product documentation content here...
   ```
3. Add a link to your new product docs in `docs/index.md` and `index.md`.

---

## 📰 How to Write a Blog Post

1. Create a new `.md` file inside the `_posts/` directory following the strict date format:
   `YYYY-MM-DD-your-post-title.md` (e.g. `_posts/2026-03-10-new-feature-announcement.md`).
2. Add post Front Matter:
   ```markdown
   ---
   layout: post
   title: "New Feature Announcement"
   date: 2026-03-10 12:00:00 +0000
   categories: [product-updates, features]
   tags: [release, update]
   ---

   Your blog post content goes here...
   ```
3. Jekyll will automatically render the blog post under `/blog/` and include it in `/blog/index.md`.

---

## 🎨 Themes & Customization Options

### 1. Built-in Theme (`minima`)
Currently configured in `_config.yml` using `theme: minima`. Standard, clean, and zero-configuration on GitHub Pages.

### 2. Upgrading to "Just the Docs" (Dedicated Docs Theme)
To switch to a documentation-first theme with instant search and sidebar navigation:
1. In `_config.yml`, replace `theme: minima` with:
   ```yaml
   remote_theme: just-the-docs/just-the-docs
   plugins:
     - jekyll-remote-theme
   ```
2. Enable GitHub Pages building on your GitHub repository under **Settings -> Pages**.

---

## 🚀 Deployment on GitHub Pages

1. Push your changes to the `main` (or default) branch.
2. Go to **Settings -> Pages** on GitHub.
3. Under **Source**, select **Deploy from a branch** and choose `main` / `(root)`.
4. GitHub Pages will build and publish your wiki site at `https://<your-username>.github.io/`.
