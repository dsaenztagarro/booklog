---
layout: default
title: Projects
permalink: /projects/
---

{% for project in site.projects %}
  <h2><a class="post-link" href="{{ project.url | prepend: site.baseurl }}">{{ project.title }}</a></h2>
{% endfor %}
