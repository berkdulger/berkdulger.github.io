---
title: Social Life
permalink: /social-life/
header:
    image: armenia_teghut-wallpaper-1920x1080.jpg
---

{% include base_path %}
{% include group-by-array collection=site.posts field="categories" %}

{% for category in group_names %}
  {% if category contains "Tech" %}
  {% assign posts = group_items[forloop.index0] %}
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
  {% endif %}
{% endfor %}