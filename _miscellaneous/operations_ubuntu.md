---
layout: post
title:  "Operations Ubuntu"
date:   2016-03-19 02:00:00 +0100
tags:
- miscellaneous
---

# Change shell

```
chsh --shell /bin/bash <username>
```

# Create user

```
sudo adduser newuser

# How To Grant a User Sudo Privileges
sudo visudo

# root    ALL=(ALL:ALL) ALL
# newuser ALL=(ALL:ALL) ALL

# Changer current user
su --shell /bin/bash - cirujanos

groupadd –r sshusers

usermod –a –G sshusers username

# /etc/ssh/sshd_config
Port 10000
MaxAuthTries 3
AllowGroups sshusers
# AllowUsers root cirujanos

# Add ssh public keys to authorized keys

service ssh restart
```

## Permissions release process

```
chown -R cirujanos:www-data /var/www/cirujanos/
```

## Start ssh agent

```
eval `ssh-agent -s`
ssh-add
```
