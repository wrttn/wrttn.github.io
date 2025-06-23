---
title: Cooking
---

{% assign recipesByCategory = site.c | group_by_exp: "c", "c.category" | where_exp: "item", "item.title != 'Cooking'" | sort: "name" %}
{% for cat in recipesByCategory %}

  {% if cat.name == nil %}No Category{% else %}{{ cat.name }}{% endif %}

  <ul class="index">
    {% for r in cat.items %}
      <li><a href="{{ r.url }}">{{ r.title }}</a></li>
    {% endfor %}
  </ul>
  
{% endfor %}
