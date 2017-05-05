---
layout: post
title:  "Operations MacOs"
date:   2016-03-19 02:00:00 +0100
tags:
- miscellaneous
---

# Check OS version

```
sw_vers
system_profiler SPSoftwareDataType
```

# Create gpg key

```
brew install gpg

gpg --gen-key
gpg --list-secret-keys --keyid-format LONG
gpg --armor --export 7BEA262B83439EC3

# Config git to use your gpg key
git config --global user.signingkey 7BEA262B83439EC3

# Create your signed commit
git commit -S -m your commit message
```

# Disable SIP to Get Your System-Level Utilities Working Again

- Reboot your Mac into Recovery Mode by restarting your computer and holding down Command+R until the Apple logo appears on your screen.
- Click Utilities > Terminal.
- In the Terminal window, type in `csrutil disable` and press Enter.
- Restart your Mac.

# Ftp settings

```
#/etc/ftp.conf
# match umask from Mac OS X Server ftpd
umask all 022
chroot all /Users/user/Ftp
```

Test with `ftp user@localhost`
