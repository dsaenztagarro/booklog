---
layout: post
title:  "MySQL"
date:   2016-12-24 18:00:00 +0100
categories: command
---

## OS X

By default, the OS X installation does not use a my.cnf, and MySQL just uses the default values. To set up your own my.cnf, you could just create a file straight in /etc.

```sql
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
FLUSH PRIVILEGES;
```
