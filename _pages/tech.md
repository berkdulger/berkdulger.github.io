---
layout: archive
title: Tech Posts
permalink: /tech/
author_profile: true
---

{% include base_path %}
{% include group-by-array collection=site.posts field="categories" %}


  {% assign posts = group_items[tech] %}
  <h2 id="{{ category | slugify }}" class="archive__subtitle">{{ category }}</h2>
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}