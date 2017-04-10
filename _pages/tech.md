---
title: Tech Posts
permalink: /tech/
header:
    image: galaxy-wallpaper-11.jpg
---

{% for category in group_names %}
  {% if category contains "Tech" %}
     {% assign posts = group_items[forloop.index0] %}
     {% for post in posts %}
        {% include archive-single.html %}
     {% endfor %}
  {% endif %}
{% endfor %}

