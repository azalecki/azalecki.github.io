---
layout: page
permalink: /repositories/
title: repositories
description: Below you will find a selection of my GitHub Repositories.
nav: true
nav_order: 2
---

{% if site.data.repositories.github_repos %}

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
