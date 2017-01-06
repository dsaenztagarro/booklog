---
layout: post
title:  "Operations"
date:   2016-03-19 02:00:00 +0100
tags:
- miscellaneous
---

# Check OS version (macos)

```
sw_vers
system_profiler SPSoftwareDataType
```

# Create gpg key (macos)

```
gpg --gen-key
gpg --list-secret-keys --keyid-format LONG
gpg --armor --export 7BEA262B83439EC3

# Config git to use your gpg key
git config --global user.signingkey 7BEA262B83439EC3

# Create your signed commit
git commit -S -m your commit message
```

# Change shell (ubuntu)

```
chsh --shell /bin/bash <username>
```

# Create user (ubuntu)

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

## Permissions release process (ubuntu)

```
chown -R cirujanos:www-data /var/www/cirujanos/
```

## Start ssh agent (ubuntu)

```
eval `ssh-agent -s`
ssh-add
```


