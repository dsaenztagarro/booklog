---
layout: post
title:  "Network"
date:   2016-03-19 02:00:00 +0100
tags:
- miscellaneous
---

### Scanning ports in remote machine

```
brew install nmap
nmap -p- -sV <ip-address>
nmap -p1-65535 -sV <ip-address>
```

### Add user to sudo group (ubuntu)

```
gpasswd -a <user> group
```

### Release ports

```
kill -9 (lsof -i tcp:9200 | awk 'NR>1{print $2}')
```
