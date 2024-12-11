---
layout: page
permalink: /repositories/
title: repositories
description: My GitHub stats & repositories.
nav: true
nav_order: 3
---
{% if site.github_username %}
<p>You can find my GitHub page <a href="https://github.com/{{ site.github_username }}"><b>here</b></a>.</p>
{% endif %}
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

## Contributions

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
