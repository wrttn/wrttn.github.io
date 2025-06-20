---
title: Reading
---

<ul class="index">
{% assign reading = site.r | where_exp: "item", "item.title != 'Reading'" %}
{% for r in reading %}
<li><a href="{{ r.url }}">{{ r.title }}</a> by {{ r.author }}</li>
{% endfor %}
</ul>
