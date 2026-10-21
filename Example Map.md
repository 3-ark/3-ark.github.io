---
title: Example Map
tags:
  - example
  - map
  - leaflet
  - visualization
source: ""
description: Interactive Leaflet map rendering examples and configuration guide.
createdat: 1791964044629
lastupdatedat: 1791964044629
pinned: false
---

# Example Map

InsightPage supports interactive maps rendered using **Leaflet.js** via ```map``` code blocks.

---

## Interactive Map Example

```map
center:
  lat: 51.505
  lng: -0.09
zoom: 13
height: 380px
markers:
  - lat: 51.505
    lng: -0.09
    title: "Central London"
    popup: "<b>Central London</b><br>Heart of the city."
    color: "#ef4444"
  - lat: 51.515
    lng: -0.1
    title: "British Museum"
    popup: "<b>British Museum</b><br>World-famous history and culture museum."
    color: "#3b82f6"
  - lat: 51.5007
    lng: -0.1246
    title: "Big Ben"
    popup: "<b>Big Ben & Houses of Parliament</b>"
    color: "#10b981"
lines:
  - coordinates:
      - [51.505, -0.09]
      - [51.515, -0.1]
      - [51.5007, -0.1246]
      - [51.505, -0.09]
    color: "#8b5cf6"
```

---

## Configuration Reference

Use YAML or JSON inside a ```map``` block:

- **`lat` / `lng`**: Latitude and longitude center coordinates.
- **`zoom`**: Initial zoom level (1 to 19).
- **`height` / `width`**: Map container dimensions (e.g. `380px`, `100%`).
- **`markers`**: List of marker objects or `[lat, lng, popup]` tuples.
  - `lat`, `lng`: Marker coordinates.
  - `popup`: HTML / text displayed on click.
  - `color`: Marker pin color (e.g., `#ef4444`, `#3b82f6`).
- **`lines` / `polylines`**: Array of lines with coordinates and color options.
- **`polygons`**: Polygon shapes with `fillColor` and `color`.
- **`circles`**: Circle overlays with `lat`, `lng`, `radius` (in meters), and `popup`.
- **`geojson`**: Raw GeoJSON object or string to plot vector layers.