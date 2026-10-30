---
layout: page
title: Product Blog & Engineering Updates
permalink: /blog/
description: "Release notes, architecture insights, and product updates from the engineering team."
---

<div class="card-grid" style="grid-template-columns: 1fr;">
  {% for post in site.posts %}
    <div class="card">
      <h2 class="card-title" style="font-size: 1.5rem;"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <div class="card-meta" style="margin-bottom: 1rem;">
        <span>📅 {{ post.date | date: "%B %d, %Y" }}</span>
        {% if post.categories %}
          <span>📁 {{ post.categories | join: ", " }}</span>
        {% endif %}
        {% if post.tags %}
          <div>
            {% for tag in post.tags %}
              <span class="tag-badge">#{{ tag }}</span>
            {% endfor %}
          </div>
        {% endif %}
      </div>
      <p class="card-description" style="font-size: 1rem;">{{ post.content | strip_html | truncatewords: 50 }}</p>
      <div>
        <a href="{{ post.url | relative_url }}" class="btn btn-secondary">Read Full Article &rarr;</a>
      </div>
    </div>
  {% endfor %}
</div>
