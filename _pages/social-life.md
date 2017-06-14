---
title: Social Life
permalink: /social-life/
header:
    image: pexels-photo-196666.jpg
---

{% if page.url != "/" and site.breadcrumbs %}
  {% unless paginator %}
    {% include breadcrumbs.html %}
  {% endunless %}
{% endif %}

  <div class="archive">
      <h1 class="page__title">{{ page.title }}</h1>
    {{ content }}
  </div>