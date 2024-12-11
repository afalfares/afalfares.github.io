---
layout: page
permalink: /repositories/
title: repositories
description: My GitHub stats & repositories. You can find my GitHub profile <a href="https://github.com/afalfares"><b>here</b></a>.
nav: true
nav_order: 3
---

{% if site.data.repositories.github_users %}

## Stats

{% if site.repo_trophies.enabled %}
{% for user in site.data.repositories.github_users %}
{% if site.data.repositories.github_users.size > 1 %}

  <h4>{{ user }}</h4>
  {% endif %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo_trophies.liquid username=user %}
  </div>
<br>
<hr>
<br>
{% endfor %}
{% endif %}
{% endif %}

{% if site.data.repositories.github_repos %}

## Repositories

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
