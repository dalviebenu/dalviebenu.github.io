---
title:  "List of my best projects"
permalink: /projects/
layout: page
---


{% for project in site.projects %}
  <h2>
    <a href="{{ project.url }}">
      {{ project.title }}
    </a>
  </h2>
{% endfor %}
