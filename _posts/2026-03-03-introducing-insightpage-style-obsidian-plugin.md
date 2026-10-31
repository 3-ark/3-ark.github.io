---
layout: post
title: "Introducing InsightPage Style: Obsidian Plugin for Rich Visualizations & Interactive Notes"
date: 2026-03-03 12:00:00 +0000
categories: [obsidian, release, plugins]
tags: [obsidian, charts, maps, timelines, abcjs, markdown, open-source]
---

We are thrilled to introduce the official Obsidian community plugin: [**InsightPage Style (`3-ark/insightpage-style`)**](https://github.com/3-ark/insightpage-style)!

InsightPage Style brings the exact same visual components and interactive diagrams powering our web assistant and note vault directly into your local **Obsidian** desktop experience.

---

## What is InsightPage Style?

While standard Markdown is great for structured text, complex technical notes often require rich visual aids—interactive timelines, responsive charts, geographic maps, musical notation, and discrete inline comments.

[InsightPage Style](https://github.com/3-ark/insightpage-style) seamlessly integrates these capabilities into Obsidian using familiar Markdown code blocks and custom syntax.

---

## Key Features & Highlights

### 1. Observable Plot & YAML Charts (`plot`, `chart`)
Render declarative data visualizations using [Observable Plot](https://observablehq.com/@observablehq/plot) and D3, or write concise YAML configurations powered by Chart.js syntax:

* **Chart.js Types**: Bar, Line, Pie, Doughnut, Radar, and Sankey diagrams.
* **Observable Plot**: Full JavaScript execution context with access to `Plot`, `d3`, and vault file loading via `fetch()`.

```chart
type: bar
labels: ["Q1", "Q2", "Q3", "Q4"]
series:
  - title: "Productivity Index"
    data: [65, 82, 90, 115]
width: 500px
```

### 2. Zoomable Event Timelines (`timeline`)
Plot milestones, multi-month development phases, and ongoing projects with interactive pan and zoom controls:
* Supports JSON, YAML, or JS object literals.
* Category filtering toggles and dynamic "Today" indicator line.
* SVG export and copy actions built-in.

### 3. Interactive Leaflet Maps (`map`, `leaflet`)
Embed interactive maps directly into your notes:
* Customizable markers, popups, and radius circles.
* Polylines and polygons for routes and zones.
* Support for custom tile servers and raw GeoJSON layers.

### 4. ABC Sheet Music Notation & Audio Player (`abc`, `abcjs`)
Write sheet music with standard ABC notation:
* Built-in interactive synthesizer audio playback (Play/Pause/Seek).
* Real-time visual note highlighting synchronized with audio playback.
* MIDI file export (`.midi`) and source copy controls.

### 5. Inline Popover Comments (`::cmt[...]`)
Add compact popover comments directly inside paragraph text:
* Compact emoji badge trigger in preview mode.
* Hover or click to reveal formatted callout notes.
* Clean print and PDF export styling.

---

## Open Source & Community

The plugin is 100% open-source under the AGPL-3.0 license.

* **GitHub Repository**: [https://github.com/3-ark/insightpage-style](https://github.com/3-ark/insightpage-style)
* **Interactive Showcase**: Explore live web demos on our [Rendering Showcase]({{ '/Rendering Showcase/' | relative_url }}).
* **Sample Visualizations**: Check out [Example Chart]({{ '/Example Chart/' | relative_url }}), [Example Map]({{ '/Example Map/' | relative_url }}), and [Example Timeline]({{ '/Example Timeline/' | relative_url }}).

Check out the repository on GitHub, try it out in your Obsidian vault, and let us know what you think!
