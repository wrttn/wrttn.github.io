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

<style>
  @media (min-width: 45rem) {           /* ≈ 720 px and up */
    main {                              /* or #content if your layout uses it */
        column-count: 3;              /* ask for up to three columns        */
        column-gap: 2rem;             /* space between the columns          */
    }

    /* keep each category together so headings don't split */
    h2, h3, ul {
        break-inside: avoid;
        -webkit-column-break-inside: avoid;
    }
}
</style>
