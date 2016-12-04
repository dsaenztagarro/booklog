---
layout: post
title:  "Ruby: Gem::Exception Unable to require openssl"
date:   2016-04-09 11:17:21 +0200
categories: ruby
---

To avoid headaches I enabled `autolibs` so all dependencies of ruby are handled by `rvm`.

```
rvm get stable
brew reinstall openssl
rvm autolibs enable
rvm install ruby
```
