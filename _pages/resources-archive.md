---
layout: archive
title: "Resources"
permalink: /resources/
author_profile: true
---

{% include group-by-array collection=site.resources field="categories" %}

{% for category in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ category | slugify }}" class="archive__subtitle">{{ category }}</h2> 
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}