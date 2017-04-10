---
title: Tech Posts
permalink: /tech/
header:
    image: galaxy-wallpaper-11.jpg
---
{% include base_path %}

<div class="archive">
{% for post in site.posts %}
    {% if post.categories contains 'Tech' %}
        {% include archive-single.html %}
    {% endif %}
{% endfor %}
</div>

