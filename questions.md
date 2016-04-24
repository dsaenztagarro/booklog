---
layout: default
title: Todos
permalink: /questions/
---

{% for question in site.questions %}
  <h2><a class="post-link" href="{{ question.url | prepend: site.baseurl }}">{{ question.title }}</a></h2>
{% endfor %}
