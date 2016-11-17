---
layout: post
title:  "Ruby"
date:   2016-11-17 05:00:00 +0100
categories: language
---

### Bundler

```
bundle config build.eventmachine --with-cppflags=-I/usr/local/opt/openssl/include
```

```
# ~/.bundle/config
---
BUNDLE_BUILD__EVENTMACHINE: "--with-cppflags=-I/usr/local/opt/openssl/include"
```
