---
layout: default
title: Categorías
permalink: /categories/
---

# Archivo por Categorías

{% assign categories = site.categories | sort %}
{% for category in categories %}
  <div id="{{ category | first | slugify }}" class="category-section">
    <h2 class="category-title">
      <span class="icon">#</span> {{ category | first }}
    </h2>
    <ul class="post-list-simple">
      {% for post in category.last %}
        <li>
          <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}