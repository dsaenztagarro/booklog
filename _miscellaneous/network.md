---
layout: post
title:  "Network"
date:   2016-03-19 02:00:00 +0100
tags:
- miscellaneous
---

- Scanning ports

```
brew install nmap
nmap -p- -sV <ip-address>
nmap -p1-65535 -sV <ip-address>
```

- Add user to sudo group

```
gpasswd -a <user> group
```
