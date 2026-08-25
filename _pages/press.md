---
layout: page
permalink: /press/
title: press
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
  {% for photo in item.images %}
    <figure class="press-figure">
      <img class="press-image" src="{{ '/assets/img/press/' | append: photo.file | relative_url }}" alt="{{ photo.caption | default: item.title | escape }}">
      {% if photo.caption %}<figcaption class="press-caption">{{ photo.caption }}</figcaption>{% endif %}
    </figure>
  {% endfor %}
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
