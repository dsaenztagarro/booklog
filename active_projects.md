---
layout: default
title: Active Projects
permalink: /active_projects/
---

{% for project in site.active_projects %}
  <h2><a class="post-link" href="{{ project.url | prepend: site.baseurl }}">{{ project.title }}</a></h2>
{% endfor %}
