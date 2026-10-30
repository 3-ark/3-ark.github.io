---
layout: page
title: Product Blog
permalink: /blog/
---

# 📰 Product Blog & Engineering Updates

Welcome to the product blog. Here we publish release notes, engineering insights, and product updates.

---

{% for post in site.posts %}
* **[{{ post.title }}]({{ post.url }})** — *{{ post.date | date: "%B %d, %Y" }}*
  {{ post.excerpt | strip_html | truncatewords: 25 }}
{% endfor %}
