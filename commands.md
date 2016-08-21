---
layout: default
title: Commands
permalink: /commands/
---

{% for command in site.commands %}
  <h2><a class="post-link" href="{{ command.url | prepend: site.baseurl }}">{{ command.title }}</a></h2>
{% endfor %}
