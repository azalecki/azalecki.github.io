---
layout: page
permalink: /teaching/
title: teaching
description: Classes, workshops, and teaching material.
nav: true
nav_order: 4
---

{% for inst in site.data.teaching %}
<h3 class="mt-4">{{ inst.institution }}</h3>

{% for course in inst.courses %}
<div class="card mt-3">
  <div class="p-3">
    <div class="d-flex justify-content-between align-items-start">
      <h5 class="font-weight-bold">{{ course.title }}</h5>
      {% if course.code %}<span class="badge bg-success">{{ course.code }}</span>{% endif %}
    </div>
    <h6 class="font-italic">{{ course.term }}</h6>
    <ul class="mb-0">
      {% for item in course.details %}
      <li>{{ item | markdownify | remove: '<p>' | remove: '</p>' }}</li>
      {% endfor %}
    </ul>
  </div>
</div>
{% endfor %}
{% endfor %}