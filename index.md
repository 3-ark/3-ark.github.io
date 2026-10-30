---
layout: home
title: Product Wiki & Engineering Hub
description: "Central portal for product documentation, engineering notes, and technical articles."
---

<div class="hero-banner">
  <div class="hero-badge">⚡ Developer & Technical Knowledge Base</div>
  <h1>Product Wiki & Engineering Hub</h1>
  <p>Discover complete user guides, system architecture diagrams, interactive visualization showcases, and engineering updates for our product ecosystem.</p>
  <div class="hero-buttons">
    <a href="{{ '/docs/' | relative_url }}" class="btn btn-primary">📖 Explore Documentation</a>
    <a href="{{ '/blog/' | relative_url }}" class="btn btn-secondary">📰 Engineering Blog</a>
    <a href="{{ '/Rendering Showcase/' | relative_url }}" class="btn btn-secondary">🎨 Interactive Showcase</a>
  </div>
</div>

<div class="section-header">
  <h2>🚀 Core Products & System Specs</h2>
  <a href="{{ '/docs/' | relative_url }}" class="section-link">View all docs &rarr;</a>
</div>

<div class="card-grid">
  <div class="card featured-card">
    <div class="card-tag">Core Product</div>
    <h3 class="card-title"><a href="{{ '/docs/insightpage/getting-started/' | relative_url }}">InsightPage Assistant</a></h3>
    <p class="card-description">AI-powered Personal Knowledge Management (PKM) browser extension with local-first Markdown vault integration, floating side panel, and hybrid RAG search.</p>
    <div class="card-footer">
      <div class="card-meta">
        <span class="badge">v2.5 Release</span>
        <span>Local AI &bull; Privacy-first</span>
      </div>
      <a href="{{ '/docs/insightpage/getting-started/' | relative_url }}" class="card-action">Get Started &rarr;</a>
    </div>
  </div>

  <div class="card">
    <div class="card-tag">Architecture & Security</div>
    <h3 class="card-title"><a href="{{ '/privacy-policy/' | relative_url }}">Privacy & Security Policy</a></h3>
    <p class="card-description">Complete overview of our zero-data collection, local-first credential management, and direct client-to-API communication model.</p>
    <div class="card-footer">
      <div class="card-meta">
        <span class="badge">100% Local-First</span>
        <span>Zero Tracking</span>
      </div>
      <a href="{{ '/privacy-policy/' | relative_url }}" class="card-action">Read Policy &rarr;</a>
    </div>
  </div>
</div>

<hr>

<div class="section-header">
  <h2>🎨 Visualizations & Markdown Rendering</h2>
  <a href="{{ '/Rendering Showcase/' | relative_url }}" class="section-link">Explore showcases &rarr;</a>
</div>

<div class="card-grid showcase-grid">
  <div class="card mini-card">
    <div class="mini-card-icon">📊</div>
    <div class="mini-card-content">
      <h3 class="card-title"><a href="{{ '/Example Chart/' | relative_url }}">Interactive Charts</a></h3>
      <p class="card-description">Bar, line, pie, donut, sankey, and radar charts via Chart.js & Observable Plot.</p>
    </div>
  </div>

  <div class="card mini-card">
    <div class="mini-card-icon">🗺️</div>
    <div class="mini-card-content">
      <h3 class="card-title"><a href="{{ '/Example Map/' | relative_url }}">Leaflet Maps</a></h3>
      <p class="card-description">Geographical coordinates, custom markers, popups, and route lines.</p>
    </div>
  </div>

  <div class="card mini-card">
    <div class="mini-card-icon">🔀</div>
    <div class="mini-card-content">
      <h3 class="card-title"><a href="{{ '/Example Mermaid/' | relative_url }}">Mermaid Diagrams</a></h3>
      <p class="card-description">Flowcharts, sequence diagrams, class diagrams, and state machines.</p>
    </div>
  </div>

  <div class="card mini-card">
    <div class="mini-card-icon">⏳</div>
    <div class="mini-card-content">
      <h3 class="card-title"><a href="{{ '/Example Timeline/' | relative_url }}">Interactive Timelines</a></h3>
      <p class="card-description">Zoomable timeline charts with milestones, tags, and category filtering.</p>
    </div>
  </div>
</div>

<hr>

<div class="section-header">
  <h2>📰 Latest Engineering Updates</h2>
  <a href="{{ '/blog/' | relative_url }}" class="section-link">View blog archive &rarr;</a>
</div>

<div class="card-grid">
  {% for post in site.posts limit:3 %}
    <div class="card">
      <h3 class="card-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <div class="card-meta" style="margin-bottom: 0.8rem;">
        <span>📅 {{ post.date | date: "%B %d, %Y" }}</span>
      </div>
      <p class="card-description">{{ post.excerpt | strip_html | truncatewords: 22 }}</p>
      <div class="card-footer" style="margin-top: auto; padding-top: 0.8rem; border-top: 1px solid var(--border-subtle);">
        <a href="{{ post.url | relative_url }}" class="card-action">Read post &rarr;</a>
      </div>
    </div>
  {% endfor %}
</div>
