---
title: Tech Posts
permalink: /tech/
header:
    image: galaxy-wallpaper-11.jpg
---


{% for post in site.posts %}
    {% if post.categories contains 'Tech' %}
            <div class="archive">
                {% include archive-single.html %}
            </div>
    {% endif %}
{% endfor %}

