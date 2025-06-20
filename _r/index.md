---
title: Reading
---

<ul class="index">
{% assign reading = site.r | where_exp: "item", "item.title != 'Reading'" %}
{% for r in reading %}
<li>
  <a href="{{ r.url }}">{{ r.title }}</a> 
  <div style="font-size: 0.9em;">by {{ r.author }}</div>
</li>
{% endfor %}
</ul>
