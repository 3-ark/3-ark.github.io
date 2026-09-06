# InsightPage Documentation & Public Pages

This repository hosts the public pages for **InsightPage** using GitHub Pages.

## Published Pages

When GitHub Pages is enabled for this repository (`3-ark.github.io`), files are automatically served as public web pages:

1. **InsightPage User Guide (Main Page)**
   - Source: `index.md` or `README.md` / `index.html`
   - URL: `https://3-ark.github.io/` (or `https://3-ark.github.io/insightpage-userguide`)

2. **Privacy Policy**
   - Source: `privacy-policy.md`
   - URL: `https://3-ark.github.io/privacy-policy` (or `https://3-ark.github.io/privacy-policy.html`)

## How to Add Additional Pages / Subpaths in GitHub Pages

To publish multiple pages or policies from the same repository on GitHub Pages:

1. **Root Markdown/HTML Files:**
   - Any `.md` or `.html` file placed in the repository root will be rendered by GitHub Pages automatically.
   - For example, `privacy-policy.md` will be accessible at `/privacy-policy` (or `/privacy-policy.html`).

2. **Directory Subpaths (`/privacy/` or `/userguide/`):**
   - You can create subdirectories containing an `index.md` or `index.html` file.
   - For example:
     - `privacy/index.md` -> accessible at `https://3-ark.github.io/privacy/`
     - `userguide/index.md` -> accessible at `https://3-ark.github.io/userguide/`
