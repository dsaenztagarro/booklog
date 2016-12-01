---
layout: post
title:  "Ruby"
date:   2016-11-17 05:00:00 +0100
categories: language
---

### WeakRef

Weak Reference class that allows a referenced object to be garbage-collected.

A WeakRef may be used exactly like the object it references.

```ruby
foo = Object.new            # create a new object instance
p foo.to_s                  # original's class
foo = WeakRef.new(foo)      # reassign foo with WeakRef instance
p foo.to_s                  # should be same class
GC.start                    # start the garbage collector
p foo.to_s                  # should raise exception (recycled)
```

### Bundler

```
bundle config build.eventmachine --with-cppflags=-I/usr/local/opt/openssl/include
```

```
# ~/.bundle/config
---
BUNDLE_BUILD__EVENTMACHINE: "--with-cppflags=-I/usr/local/opt/openssl/include"
```

### Update the RubyGems system software

Check [RubyGems blog](http://blog.rubygems.org) for updates

```
gem update --system 2.6.8
```
