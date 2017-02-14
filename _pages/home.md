---
layout: splash
permalink: /
author_profile: true

header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/rainy_weather-wallpaper-1920x1080.jpg
  caption:
---

{% include base_path %}
{% include group-by-array collection=site.posts field="categories" %}


  {% assign posts = group_items[tech] %}
  <h2 id="{{ category | slugify }}" class="archive__subtitle">{{ category }}</h2>
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
