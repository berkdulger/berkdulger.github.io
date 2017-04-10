---
title: Tech Posts
permalink: /tech/
layout: archive
header:
    image: galaxy-wallpaper-11.jpg
---

{% include archive.html %}
{% for post in site.posts %}
    {% if post.categories contains 'Tech' %}
        {% include archive-single.html %}
    {% endif %}
{% endfor %}


