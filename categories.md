---
layout: page
permalink: /categories/
title: Список рубрик
---

<ul class="category-list">
{% assign categories_list = site.categories %}
    {% for category in categories_list %}
      {% for cat in site.data.categories %}
          {% if category[0] == cat.slug %}
            <li class="category-title"><a href="/category/{{cat.slug}}" class="category-meta">{{cat.name}} ({{category[1].size}})</a></li>
          {% endif %}
        {% endfor %}
    {% endfor %}
        
{% assign categories_list = nil %}
</ul>
