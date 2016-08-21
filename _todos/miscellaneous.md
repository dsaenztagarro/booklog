---
layout: post
title:  "Miscellaneous"
date:   2016-03-21 05:00:00 +0100
categories: todo
---

- [Shell config subfiles](http://blog.sanctum.geek.nz/shell-config-subfiles/)

```bash
# Load any supplementary scripts
for config in "$HOME"/.bashrc.d/*.bash ; do
    source "$config"
done
unset -v config
```
