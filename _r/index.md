---
title: Reading
---

<ul class="index">
{% assign reading = site.r | where_exp: "item", "item.title != 'Reading'" %}
{% for r in reading %}
<li>
  <a href="{{ r.url }}">{{ r.title }}</a> 
  <div style="margin-top: -4px; font-size: 0.9em;">{{ r.author }}</div>
</li>
{% endfor %}
</ul>
