# Product Wiki & Developer Hub (3-ark.github.io)

Central engineering hub, product documentation, and interactive visualization portal powered by Jekyll and GitHub Pages.

---

## 🚀 Overview

This repository hosts the official documentation, interactive demos, and developer updates for projects maintained under **3-ark**:

* **[InsightPage Assistant](docs/insightpage/getting-started.md)**: AI-powered Personal Knowledge Management (PKM) browser extension with side panel chat, floating window, and local markdown vault sync.
* **[InsightPage Style](https://github.com/3-ark/insightpage-style)**: Official Obsidian community plugin bringing rich charts (Chart.js & Observable Plot), interactive timelines, Leaflet maps, ABC sheet music audio, and inline popover comments to markdown notes.
* **[N-Gram Cipher](docs/ngram-cipher/)**: Natural English N-Gram steganographic cipher encoder and decoder in JavaScript / TypeScript (AES-256-GCM + dynamic N-Gram statistical language models).

---

## 🏗️ Repository Architecture

```text
├── _config.yml         # Jekyll configuration (theme, title, plugins, permalinks)
├── index.md            # Home portal page linking to docs, blog, and showcases
├── WIKI_GUIDE.md       # Product wiki and blog management guide
├── docs/               # Product Documentation Hub
│   ├── index.md        # Docs hub directory
│   ├── insightpage/    # InsightPage Assistant documentation
│   └── ngram-cipher/   # N-Gram Cipher documentation and interactive demo
├── blog/
│   └── index.md        # Engineering blog archive
├── _posts/             # Jekyll blog posts (YYYY-MM-DD-title.md)
├── assets/
│   ├── css/            # Site styling and visualization stylesheets
│   └── js/             # Bundled libraries (insightpage-style, pele, ngram-cipher)
└── _layouts/           # Jekyll layouts (default, home, page, post)
```

---

## 💻 Local Development

### Prerequisites
- Ruby 3.2+
- Bundler / Jekyll

### Running Locally

```bash
# Add user gem directory to PATH (if needed)
export PATH="$HOME/.local/share/gem/ruby/3.2.0/bin:$PATH"

# Build static site output
jekyll build

# Run local preview server
jekyll serve
```

The site will be available at `http://localhost:4000/`.

---

## 📄 License

This repository and documentation site are available under the MIT License.
