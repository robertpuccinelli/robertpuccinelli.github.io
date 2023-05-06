---
title: Instrumentation
layout: splash
permalink: /instrumentation/

header:
  overlay_color: "#000"
  overlay_filter: "0.0"
---
## builds

{% include group-by-array collection=site.posts field="categories" %}

{% for category in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  {% if category == 'build' %}
    {% for post in posts %}
      {% include archive-single.html %}
    {% endfor %}
  {% endif %}
{% endfor %}

## guides

{% for category in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  {% if category == 'guide' %}
    {% for post in posts %}
      {% include archive-single.html %}
    {% endfor %}
  {% endif %}
{% endfor %}
