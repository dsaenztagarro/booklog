---
layout: default
title: Todos
permalink: /todos/
---

{% for todo in site.todos %}
  <h2><a class="post-link" href="{{ todo.url | prepend: site.baseurl }}">{{ todo.title }}</a></h2>
{% endfor %}
