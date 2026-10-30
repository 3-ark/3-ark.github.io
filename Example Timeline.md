---
source: ""
description: Interactive timeline chart examples illustrating loose JSON and unquoted YAML syntax support in InsightPage.
title: Example Timeline
tags:
  - example
  - timeline
  - chart
  - visualization
createdat: 1792555335093
lastupdatedat: 1792555335093
pinned: false
---

# Example Timeline

InsightPage supports interactive zoomable timelines rendered using `timeline`, `timeline-chart`, or `event-timeline` code blocks.

---

## 1. Interactive Timeline Example (YAML Syntax)

Standard YAML supports unquoted keys and strings:

```timeline
- start: 2013-10-01
  end: 2016-09-30
  institution: Technical University Dresden
  title: BSc. Student in Computer Science
  type: education
  collection: []

- start: 2016-10-01
  end: 2019-01-31
  institution: Technical University Dresden
  title: MSc. Student in Computer Science
  type: education
  collection: [Glyphboard, Conversation Trainer, VisBlocks]

- start: 2019-03-01
  end: 2022-02-26
  institution: Aarhus University
  title: Ph.D. Student
  type: academia
  collection: [ProSample, ProSteer, ReVize, ReVis, ReData]

- start: 2022-03-01
  end: Date.now()
  institution: Aarhus University
  title: Postdoctoral Researcher
  type: academia
  collection: [MapBlender]
```

---

## 2. Loose Syntax Support Examples

InsightPage intelligently parses loose JSON and YAML syntaxes without strict quotes, including:
- Loose double braces `{...}` or single object `{ ... }`
- Unquoted strings without double quotes
- Variable key-value spacing (with or without spaces after `:`)
- Dynamic `Date.now()` timestamps (rendering the "Today" indicator line)

### Loose Double-Brace Object

```timeline
{start: 2020-01-01, title:Project Alpha Launch, type:milestone, end: 2021-06-01, collection:[Design, Prototype]}
```

### Loose Object Array with Date.now()

```timeline
[
  {start: 2021-01-01,end: 2022-05-15,title:"Research Phase",category:R&D,collection:["Survey","Paper"]},
  {start: "2022-06-01",end: Date.now(),title:Product Rollout,category:Operations,collection:[V1,V2]}
]
```

---

## 3. Configuration Reference

Specify events using JSON or YAML arrays:
- **`start`**: Event start date (ISO string `YYYY-MM-DD` or timestamp).
- **`end`**: Event end date (optional; omitted end dates or `Date.now()` extend to present day). Using `Date.now()` renders the vertical "Today" indicator line.
- **`title`**: Title label displayed above the event bar.
- **`collection`**: Array of related project or publication tags. Multiple items collapse into a `+N` badge on tight zoom.
- **`[customCategory]`**: Any custom key (e.g., `type`, `institution`, `category`) is automatically discovered and mapped to color categories with category selection radio buttons.
