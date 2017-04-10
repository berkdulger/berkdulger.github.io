---
title: Social Life
permalink: /social-life/
header:
    image: pexels-photo-196666.jpg
---

{% include base_path %}
{% include group-by-array collection=site.posts field="categories" %}

{% for category in group_names %}
  {% if category contains "Social" %}
  {% assign posts = group_items[forloop.index0] %}
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
  {% endif %}
{% endfor %}