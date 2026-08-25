---
layout: page
permalink: /press/
title: press
description: media coverage of our research and activities.
nav: true
nav_order: 6
---

<!-- Content lives in _data/press.yml; images in assets/img/press/ -->

{% assign items = site.data.press | sort: "date" | reverse %}

{% if items and items.size > 0 %}
  {% for item in items %}
<article class="press-item">
  <h5 class="press-title">{{ item.title }}</h5>
  <p class="press-date">{{ item.date | date: "%Y.%m.%d" }}</p>
  {% if item.image %}
    <img class="press-image" src="{{ '/assets/img/press/' | append: item.image | relative_url }}" alt="{{ item.title | escape }}">
    {% if item.caption %}<p class="press-caption">{{ item.caption }}</p>{% endif %}
  {% endif %}
  {% if item.summary %}<div class="press-summary">{{ item.summary | markdownify }}</div>{% endif %}
  {% if item.outlets %}
    <p class="press-outlets">
      <span class="press-outlets-label">보도 매체</span>
      {% for outlet in item.outlets %}
      <span class="press-outlet">{{ outlet }}</span>
      {% endfor %}
      {% if item.outlets_note %}<span class="press-outlets-note">{{ item.outlets_note }}</span>{% endif %}
    </p>
  {% endif %}
</article>
  {% endfor %}
{% else %}
<p>준비 중입니다.</p>
{% endif %}
