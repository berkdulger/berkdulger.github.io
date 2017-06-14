---
layout: archive
title: Tech Posts
permalink: /tech/
header:
    image: galaxy-wallpaper-11.jpg
---

{% include base_path %}
{% include group-by-array collection=site.posts field="categories" %}

{% var searchArray = ['Tech']; %}

{% for category in searchArray %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ category | slugify }}" class="archive__subtitle">{{ category }}</h2>
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}

