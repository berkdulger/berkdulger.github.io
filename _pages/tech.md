---
title: Tech Posts
permalink: /tech/
header:
    image: galaxy-wallpaper-11.jpg
---

<ul class="posts">
{% for post in site.posts %}
    {% if post.categories contains 'Tech' %}
        <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
            {% include archive-single.html %}
    {% endif %}
{% endfor %}
</ul>
