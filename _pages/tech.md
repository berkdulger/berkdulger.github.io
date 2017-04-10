---
title: Tech Posts
permalink: /tech/
header:
    image: galaxy-wallpaper-11.jpg
---

<h3 class="archive__subtitle">{{ site.data.ui-text[site.locale].recent_posts | default: "Recent Posts" }}</h3>

{% include base_path %}
{% include group-by-array collection=site.posts field="categories" %}

{% for category in group_names %}
  {% if category contains "Tech" %}
      {% assign posts = group_items[forloop.index0] %}
      {% for post in posts %}
        {% for post in paginator.posts %}
            {% include archive-single.html %}
        {% endfor %}
      {% endfor %}
  {% endif %}
{% endfor %}

{% include paginator.html %}