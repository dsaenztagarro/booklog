---
layout: post
title:  "Python"
date:   2016-12-06 05:00:00 +0100
categories: language
---

# Virtualenv

```
# Project
virtualenv -p /usr/local/bin/python3.5 venv

# Fabric requires python 2.7
# You will need to activate this environment from your project
# Keep virtualenv requirements in a separate file (requirements_fabric.txt)
cd ~/Code/Python/Virtualenvs/
virtualenv -p /usr/local/bin/python2.7 fabric
```

# pip

```bash
# src/_fastmath.c:36:11: fatal error: 'gmp.h' file not found
CFLAGS="/absolute/path/include" pip install -r requirements.txt

# ld: library not found for -lgmp
LDFLAGS="/absolute/path/lib" pip install -r requirements.txt
```

# Links

[Python 3.5 documentation](https://docs.python.org/3.5/)
[27.3. pdb — The Python Debugger](https://docs.python.org/3/library/pdb.html)
