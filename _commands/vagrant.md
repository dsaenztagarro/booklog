---
layout: post
title:  "Vagrant"
date:   2017-01-15 18:00:00 +0100
categories: command
---

```
vagrant package --base oracle-java8
```

Where `oracle-java8` comes from:

```ruby
# Vagrantfile

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    # vb.gui = true

    # Customize the amount of memory on the VM:
    # vb.memory = "1024"

    vb.name = "oracle-java8"
  end
```
