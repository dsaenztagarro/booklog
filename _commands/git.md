---
layout: post
title:  "Git"
date:   2016-04-24 18:00:00 +0100
categories: command
---

### Re-applying previous commits in Git

If a new commit somehow overrides the changes from a previous commit, then you can re-apply the previous commit over the current one by using the cherry-pick command.

First, find the hash of the commit you want to re-apply, then apply it.

```bash
git log
git cherry-pick hash
```
