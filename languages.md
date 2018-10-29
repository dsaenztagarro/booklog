---
layout: default
title: Languages
permalink: /languages/
---

{% for language in site.languages %}
  <h2><a class="post-link" href="{{ language.url | prepend: site.baseurl }}">{{ language.title }}</a></h2>
{% endfor %}
