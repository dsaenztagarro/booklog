---
layout: post
title:  "C"
date:   2016-03-21 05:00:00 +0100
categories: language
---

### Parsing string options

```c
#include <string.h> // for strtok

  char *token = strtok(input, ",");
  while(token) {
          puts(token);
          token = strtok(NULL, ",");
  }
```
