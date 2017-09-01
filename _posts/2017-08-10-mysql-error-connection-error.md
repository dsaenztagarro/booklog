---
layout: post
title:  "Mysql2::Error: connection error"
date:   2017-08-10 15:53:00 +0200
categories: mysql
---

### Problem

I found this error while running my Rails suite:

```
Mysql2::Error:
  Can't connect to local MySQL server through socket '/tmp/mysql.sock' (2)
```
### How I fix it

```
$ ps ax | grep mysql | grep -v grep | awk '{print $1}' | xargs kill -9
```

### Explanation

The error seemed to be related with multiple MySQL server instances running.