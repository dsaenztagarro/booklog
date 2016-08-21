---
layout: default
title: Miscellaneous
permalink: /miscellaneous/
---

{% for item in site.miscellaneous %}
  <h2><a class="post-link" href="{{ item.url | prepend: site.baseurl }}">{{ item.title }}</a></h2>
{% endfor %}
