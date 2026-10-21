---
source: ""
description: Interactive examples and guidelines for Mermaid diagram rendering in InsightPage.
title: Example Mermaid
tags:
  - example
  - mermaid
  - diagram
  - flowchart
createdat: 1790759208075
lastupdatedat: 1792507748625
pinned: false
fileextension: .md
fileExtension: .md
---

InsightPage supports rendering vector diagrams directly in your notes using **Mermaid**.

---

## Supported Diagram Types

The following standard Mermaid diagram types are fully supported:
- **Flowcharts** (`graph` / `flowchart`)
- **Sequence Diagrams** (`sequenceDiagram`)
- **Class Diagrams** (`classDiagram`)
- **State Diagrams** (`stateDiagram-v2`)
- **Entity Relationship Diagrams** (`erDiagram`)
- **Gantt Charts** (`gantt`)
- **Git Graphs** (`gitGraph`)

> [!Note] Omitted Diagram Types & Superior Alternatives
> Heavy specialized Mermaid chart modules (`xychart`, `pie`, `journey`, `architecture`, `mindmap`) are intentionally omitted to keep extension bundle size lightweight and eliminate CPU rendering spikes:
> - **For charts & graphs:** Use **Chart.js style syntaxes** (`chart` code block) or **Observable Plot** (`plot` or `cosyobservableplot` code block). They provide far superior visual rendering, crisp SVG vector scaling, rich interactivity, and responsive layout compared to Mermaid's static chart output. See: 👉 **[[Example Chart]]**.
> - **For mindmaps:** Use the built-in interactive **Mindmap Viewer** (powered by Markmap) for a smooth, zoomable, and collapsible mind-mapping experience.

---

## Flowchart Example

```mermaid
graph TD;
    A[Start Research] --> B{Need AI Insights?};
    B -- Yes --> C[Use InsightPage Assistant];
    C --> D[Save Findings to Vault];
    B -- No --> D;
```

---

## Sequence Diagram Example

```mermaid
sequenceDiagram
    autonumber
    actor User as User
    participant CP as Side Panel
    participant AI as AI Engine
    participant FS as Local Markdown Vault

    User->>CP: Ask question
    CP->>AI: Send prompt & context
    AI-->>CP: Stream AI response
    CP->>FS: Save response to note
```

---

## State Diagram Example

```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Processing: Receive Query
    Processing --> Rendering: Generate Output
    Rendering --> Idle: Render Complete
```

---

## Gantt Chart Example

```mermaid
gantt
    title Project Timeline
    dateFormat  YYYY-MM-DD
    section Research
    Literature Review   :a1, 2026-01-01, 7d
    Data Collection     :after a1, 10d
    section Development
    System Design       :a2, 2026-01-15, 10d
    Implementation      :after a2, 14d
```

## Timeline

```mermaid
timeline TD
        title England's History Timeline
        section Stone Age
          7600 BC : Britain's oldest known house was built in Orkney, Scotland
          6000 BC : Sea levels rise and Britain becomes an island.<br> The people who live here are hunter-gatherers.
        section Bronze Age
          2300 BC : People arrive from Europe and settle in Britain. <br>They bring farming and metalworking.
                  : New styles of pottery and ways of burying the dead appear.
          2200 BC : The last major building works are completed at Stonehenge.<br> People now bury their dead in stone circles.
                  : The first metal objects are made in Britain.Some other nice things happen. it is a good time to be alive.
```

```timeline
 [{start: "2022-03-01", end: Date.now(), test: "a", institution: "Aarhus University", title: "Postdoctoral Researcher", type: "academia", collection: ["mapblender"]},
  {start: "2019-03-01", end: "2022-02-26", test: "a", institution: "Aarhus University", title: "Ph.D. Student", type: "academia", collection: ["ProSample", "ProSteer", "ReVize", "ReVis", "ReData", "ColorBrewer-lite", "VisFlow-lite"]},
  {start: "2016-10-01", end: "2019-01-31", test: "b", institution: "Technical University Dresden", title: "MSc. Student in Computer Science", type: "education", collection: ["Glyphboard", "Conversation Trainer", "VisBlocks"]},
  {start: "2013-10-01", end: "2016-09-30", test: "a", institution: "Technical University Dresden", title: "BSc. Student in Computer Science", type: "education", collection: []},
  {start: "2021-01-01", end: "2021-04-30", test: "b", institution: "Carnegie Mellon University", title: "Visiting Ph.D. student at DIG Lab", type: "academia", collection: ["ProInterest"]},
  {start: "2016-10-02", end: "2018-03-30", test: "a", institution: "Technical University Dresden", title: "Web developer", type: "academia", collection: []},
  {start: "2017-09-01", end: "2019-01-31", test: "a", institution: "SAP", title: "Part-time developer", type: "industry", collection: ["Parallel Hierarchies"]}]
```

```timeline
- start: 2022-03-01
  end: 2024-01-01
  institution: Aarhus University
  title: Postdoctoral Researcher
  type: academia
  test: a
  collection: [mapblender]

- start: 2019-03-01
  end: 2022-02-26
  institution: Aarhus University
  title: Ph.D. Student
  type: academia
  test: a
  collection: [ProSample, ProSteer, ReVize, ReVis, ReData, ColorBrewer-lite, VisFlow-lite]

- start: 2016-10-01
  end: 2019-01-31
  institution: Technical University Dresden
  title: MSc. Student in Computer Science
  type: education
  test: b
  collection: [Glyphboard, Conversation Trainer, VisBlocks]

- start: 2017-09-01
  end: 2019-01-31
  institution: SAP
  title: Part-time developer
  type: industry
  test: a
  collection: [Parallel Hierarchies]
```
