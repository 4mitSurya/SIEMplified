---
layout: default
title: SIEMplified
---

Welcome to **SIEMplified**, your go-to blog for simplifying SIEM technologies including ArcSight, Splunk, Elastic, and more.

### Filter Posts by Tag

{% include tag-filter.html %}

### Latest Posts

<ul>
{% for post in site.posts %}
  <li class="post-item" data-tags="{{ post.tags | join: ',' }}">
    <a href="{{ post.url }}">{{ post.title }}</a> — {{ post.date | date: "%b %-d, %Y" }}

    {% assign words = post.content | number_of_words %}
    {% assign reading_time = words | divided_by: 200 %}
    {% if reading_time < 1 %}
      <br><small>Reading time: less than a minute</small>
    {% else %}
      <br><small>Reading time: {{ reading_time }} minute{% if reading_time > 1 %}s{% endif %}</small>
    {% endif %}

    {% if post.tags %}
      <br>Tags: 
      {% for tag in post.tags %}
        <span style="background:#eee; padding:2px 6px; margin-right:4px; border-radius:3px;">{{ tag }}</span>
      {% endfor %}
    {% endif %}
  </li>
{% endfor %}
</ul>
