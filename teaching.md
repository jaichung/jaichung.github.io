---
layout: page
title: Teaching
permalink: /teaching/
---

{% comment %} Edit _data/teaching.yml to add or change courses. {% endcomment %}
<ul class="entries">
  {% for c in site.data.teaching %}
  <li class="entry">
    <div class="entry-main">
      <p class="entry-title">{{ c.course }}</p>
      {% capture meta %}{% if c.role and c.role != "" %}{{ c.role }}{% endif %}{% if c.role and c.role != "" and c.school and c.school != "" %} · {% endif %}{% if c.school and c.school != "" %}{{ c.school }}{% endif %}{% endcapture %}
      {% if meta != "" %}<p class="entry-meta">{{ meta }}</p>{% endif %}
      {% if c.note and c.note != "" %}<p class="entry-meta">{{ c.note | markdownify | remove: '<p>' | remove: '</p>' | strip }}</p>{% endif %}
    </div>
    {% if c.term and c.term != "" %}<div class="entry-side">{{ c.term }}</div>{% endif %}
  </li>
  {% endfor %}
</ul>
