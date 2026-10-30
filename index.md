---
layout: home
title: Product Wiki & Engineering Hub
description: "Central portal for product documentation, engineering notes, and technical articles."
---

<div class="hero-banner">
  <h1>Product Wiki & Engineering Hub</h1>
  <p>Discover complete user guides, system architecture diagrams, and release updates for our product ecosystem.</p>
  <div class="hero-buttons">
    <a href="{{ '/docs/' | relative_url }}" class="btn btn-primary">📖 Explore Documentation</a>
    <a href="{{ '/blog/' | relative_url }}" class="btn btn-secondary">📰 Read Engineering Blog</a>
  </div>
</div>

<h2>🚀 Active Product Ecosystem</h2>
<div class="card-grid">
  <div class="card">
    <h3 class="card-title"><a href="{{ '/docs/insightpage/getting-started.md' | relative_url }}">InsightPage Assistant</a></h3>
    <p class="card-description">AI-powered Personal Knowledge Management (PKM) browser extension with local-first Markdown vault integration.</p>
    <div class="card-meta">
      <span>v2.5 Release</span> &bull; <span>Local AI / Cloud</span>
    </div>
  </div>

  <div class="card">
    <h3 class="card-title"><a href="{{ '/Rendering Showcase/' | relative_url }}">Rendering & Visualizations</a></h3>
    <p class="card-description">Interactive Chart.js, Observable Plot, Leaflet Maps, Mermaid diagrams, and KaTeX math formulas showcase.</p>
    <div class="card-meta">
      <span>Rich Markdown</span> &bull; <span>Visualizations</span>
    </div>
  </div>

  <div class="card">
    <h3 class="card-title"><a href="{{ '/privacy-policy.md' | relative_url }}">Privacy & Security Policy</a></h3>
    <p class="card-description">Complete overview of our zero-data collection, local-first credentials, and direct client-to-API architecture.</p>
    <div class="card-meta">
      <span>100% Local-First</span> &bull; <span>Zero Tracking</span>
    </div>
  </div>
</div>

<hr>

<h2>📰 Latest Blog Posts</h2>
<div class="card-grid">
  {% for post in site.posts limit:3 %}
    <div class="card">
      <h3 class="card-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <div class="card-meta" style="margin-bottom: 0.8rem;">
        <span>📅 {{ post.date | date: "%B %d, %Y" }}</span>
      </div>
      <p class="card-description">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
      <div>
        <a href="{{ post.url | relative_url }}" style="font-size: 0.9rem; font-weight: 600;">Read post &rarr;</a>
      </div>
    </div>
  {% endfor %}
</div>
