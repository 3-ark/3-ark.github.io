---
source: ""
description: A showcase of the rich text rendering capabilities of the note vault.
title: Rendering Showcase
tags:
  - example
  - rendering
  - markdown
  - katex
createdat: 1790759208074
lastupdatedat: 1790916001826
pinned: false
fileextension: .md
fileExtension: .md
---
> [!Summary] Markdown Syntaxes
> This ^**note**^ *demonstrates* ~the~ various ==***"Markdown"***== rendering capabilities of InsightPage ~~***"笔记"***~~, powered by the open-source Obsidian plugin [`3-ark/insightpage-style`](https://github.com/3-ark/insightpage-style).

## Standard Markdown

InsightPage is designed to make capturing and reading web pages easier with lightweight and intuitive editing features. Standard Markdown syntaxes are fully supported in an easy-to-read layout.

> "The important thing is not to stop questioning. Curiosity has its own reason for existence."
>
> – Albert Einstein::cmt[Who knows. This is for your information; I am not sure if Einstein[^1] actually said that.]

[^1]: Jeffery, is this you?

### Editable Tables

| Feature | Supported | Notes |
| --- | :---: | --- |
| Editable Tables | ✅ | Great for structured data. |
| Chart | ✅ | Good for chart rendering. |
| Mermaid Diagrams | ✅ | See below for a cool example. |
| LaTeX Math | ✅ | For all your scientific notation needs. |
| Code Highlighting | ✅ | For sharing code snippets. |
| Native Tabs | ✅ | For a clean layout. |

## Advanced Rendering

### Tabs Inside a Note

Here is the format for internal tabs:

````
```tabs
--- tab1

$$\begin{aligned} \nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\ \nabla \cdot \mathbf{B} &= 0 \\ \nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} \\ \nabla \times \mathbf{B} &= \mu_0 \mathbf{J} + \mu_0 \varepsilon_0 \frac{\partial \mathbf{E}}{\partial t} \end{aligned}$$
--- tab2
~~***right***~~ <big>formatted</big> **bold** H~2~O X^2^=3

--- tab3
Standard Highlight: Parse ==text== directly into an HTML <mark>text</mark> tag, enabling nested formatting like ==***text***==, ==**text**==, and ==*text*==.
```
````

#### Rendered

```tabs
--- tab1

$$\begin{aligned} \nabla \cdot \mathbf{E} &= \frac{\rho}{\varepsilon_0} \\ \nabla \cdot \mathbf{B} &= 0 \\ \nabla \times \mathbf{E} &= -\frac{\partial \mathbf{B}}{\partial t} \\ \nabla \times \mathbf{B} &= \mu_0 \mathbf{J} + \mu_0 \varepsilon_0 \frac{\partial \mathbf{E}}{\partial t} \end{aligned}$$
--- tab2
~~***right***~~ <big>formatted</big> **bold** H~2~O X^2^=3

--- tab3
Standard Highlight: Parse ==text== directly into an HTML <mark>text</mark> tag, enabling nested formatting like ==***text***==, ==**text**==, and ==*text*==.
```

### Mermaid Diagrams

InsightPage supports standard Mermaid diagrams (flowcharts, sequence diagrams, class diagrams, state diagrams, ER diagrams, gantt charts, and git graphs).

To prevent CPU spikes and improve rendering performance, heavy diagram showcases are separated into dedicated notes:
👉 [**Example Mermaid Diagrams**]({{ '/Example Mermaid/' | relative_url }})

> [!Note] Optimization & Superior Alternatives
> Heavy specialized Mermaid chart modules (`xychart`, `pie`, `journey`, `architecture`, `mindmap`) are intentionally omitted to keep extension bundles lightweight and eliminate CPU rendering spikes:
> - **For charts & graphs:** Use **Chart.js style syntaxes** (`chart` code block) or native **Observable Plot** (`plot` or `cosyobservableplot` code block), which offer far superior visual rendering, crisp SVG vector scaling, rich interactivity, and responsive scaling compared to Mermaid static charts. See: 👉 [**Example Interactive Charts**]({{ '/Example Chart/' | relative_url }}).
> - **For mindmaps:** The built-in interactive **Mindmap Viewer** (powered by Markmap) delivers a significantly smoother, zoomable, and collapsible mind-mapping experience.

### Charts & Data Visualizations

InsightPage renders interactive charts via Chart.js-style YAML configurations (`chart`) and declarative JavaScript data visualizations via Observable Plot (`plot` / `cosyobservableplot`).

#### Observable Plot Syntaxes & Examples

Use `plot` or `cosyobservableplot` for declarative data visualizations powered by Observable Plot.

````markdown
```plot
Plot.rectY(
  [2, 3, 3, 4, 4, 4, 5, 5, 5, 5, 6, 6, 6, 7, 7, 8, 9, 10, 12, 15],
  Plot.binX(
    { y: "count" },
    { x: (d) => d, fill: "#3b82f6", tip: true, rx: 3 }
  )
)
```
````

**Rendered Plot:**

```plot
Plot.rectY(
  [2, 3, 3, 4, 4, 4, 5, 5, 5, 5, 6, 6, 6, 7, 7, 8, 9, 10, 12, 15],
  Plot.binX(
    { y: "count" },
    { x: (d) => d, fill: "#3b82f6", tip: true, rx: 3 }
  )
)
```

#### YAML Chart Syntaxes & Examples

Use `chart` with YAML configuration for standard bar, line, pie, and radar charts:

````markdown
```chart
type: bar
labels: ["Q1", "Q2", "Q3", "Q4"]
series:
  - title: "Revenue"
    data: [120, 150, 180, 220]
width: 500px
```
````

**Rendered Chart:**

```chart
type: bar
labels: ["Q1", "Q2", "Q3", "Q4"]
series:
  - title: "Revenue"
    data: [120, 150, 180, 220]
width: 500px
```

To explore advanced multi-series charts, donuts, Sankey diagrams, and NOAA-style plots, see:
👉 [**Example Interactive Charts**]({{ '/Example Chart/' | relative_url }})

### ABC Sheet Music Notes

Render interactive sheet music with `abc` code blocks:

````
```abc
X: 1
T: Ode to Joy
M: 4/4
L: 1/4
K: C
E E F G | G F E D | C C D E | E3/2 D/ D2 |
```
````

**Rendered Sheet Music:**

```abc
X: 1
T: Ode to Joy
M: 4/4
L: 1/4
K: C
E E F G | G F E D | C C D E | E3/2 D/ D2 |
```

### Inline Comment

Here is an example of an interactive comment callout:
::cmt[💡 example. This is a comment.]
::cmt [💡 example. This is a comment.]
::cmt{💡 example. This is a comment.}
::cmt {💡 example. This is a comment.}

Use `::cmt[]` for interactive comments/popovers.

```markdown
::cmt[💡 example. This is a comment.]
```
