---
layout: page
title: Teaching
permalink: /teaching/
statement_title: Teaching Approach
# Set to "top" to show the teaching approach above the course lists
statement_position: top
---

{% assign t = site.data.teaching %}

{% capture statement %}
{% if t.statement and t.statement != "" %}
<h2>{{ page.statement_title }}</h2>
<p class="teaching-statement">{{ t.statement }}</p>
{% endif %}
{% endcapture %}

{% if page.statement_position == "top" %}{{ statement }}{% endif %}

{% if t.instructor and t.instructor.size > 0 %}
<h2>Instructor of Record</h2>
<ul class="entries">
  {% for c in t.instructor %}
  <li class="entry entry-course">
    <div class="entry-main">
      <p class="entry-title">{{ c.course }}</p>
      {% capture meta %}{{ c.school }}{% if c.size and c.size != "" %} · {{ c.size }}{% endif %}{% endcapture %}
      {% if meta != "" %}<p class="entry-meta">{{ meta }}</p>{% endif %}
      {% if c.highlights and c.highlights != "" %}<p class="entry-highlights">{{ c.highlights | markdownify | remove: '<p>' | remove: '</p>' | strip }}</p>{% endif %}
      {% if c.feedback and c.feedback.size > 0 %}
      <div class="feedback">
        <p class="feedback-label">Selected student feedback</p>
        {% for q in c.feedback %}<blockquote>“{{ q }}”</blockquote>{% endfor %}
      </div>
      {% endif %}
    </div>
    {% if c.term and c.term != "" %}<div class="entry-side">{{ c.term }}</div>{% endif %}
  </li>
  {% endfor %}
</ul>
{% endif %}

{% if t.assistant and t.assistant.size > 0 %}
<h2>Teaching Assistant</h2>
{% assign prev = "" %}
{% for c in t.assistant %}
  {% if c.school != prev %}
    {% unless forloop.first %}</ul>{% endunless %}
<h3 class="entries-school">{{ c.school }}</h3>
<ul class="entries entries-compact">
    {% assign prev = c.school %}
  {% endif %}
  <li class="entry">
    <div class="entry-main">
      <p class="entry-title">{{ c.course }}</p>
      {% if c.highlights and c.highlights != "" %}<p class="entry-highlights">{{ c.highlights | markdownify | remove: '<p>' | remove: '</p>' | strip }}</p>{% endif %}
    </div>
    {% if c.term and c.term != "" %}<div class="entry-side">{{ c.term }}</div>{% endif %}
  </li>
  {% if forloop.last %}</ul>{% endif %}
{% endfor %}
{% endif %}

{% if page.statement_position != "top" %}{{ statement }}{% endif %}

