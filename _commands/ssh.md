---
layout: post
title:  "ssh"
date:   2016-04-24 18:00:00 +0100
categories: command
---

# Reload ssh-agent with all shh keys

```
eval `ssh-agent -s`
ssh-add -A
```

# Adding a Private Key to Your Mac OSX Keychain

On Mac OSX, the native SSH client can use the built-in keychain directly. To add your private key to the keychain simply use the command:

```
ssh-add -K /path/of/private/key

# Example
ssh-add -K ~/.ssh/id_rsa
```

# Update passphrase for private key

```
ssh-keygen -f ~/.ssh/id_rsa -p
```

# References

- [OpenBSD](http://www.openbsd.org/)
- [OpenSSH](http://www.openssh.com/)
