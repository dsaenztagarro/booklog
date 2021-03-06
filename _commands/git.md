---
layout: post
title:  "Git"
date:   2016-04-24 18:00:00 +0100
categories: command
---

```
gitk --follow db/schema.rb

# Checkout file from specific branch
git show remote_name/branch_name:path_to_file > path_to_file
```

### Re-applying previous commits in Git

If a new commit somehow overrides the changes from a previous commit, then you can re-apply the previous commit over the current one by using the cherry-pick command.

First, find the hash of the commit you want to re-apply, then apply it.

```bash
git log
git cherry-pick hash
```
You can use git cherry-pick to accept only the specific remote commits you want

### How to preview git-pull without doing fetch?

```bash
git fetch
# to show the log entries between your last common commit and the origin branch
git log HEAD...origin
# to show the diffs
git diff HEAD...origin
```

### delete all remote branches that have already been merged into master

```bash
$ git branch -r --merged |
  grep origin |
  grep -v '>' |
  grep -v master |
  xargs -L1 |
  awk '{split($0,a,"/"); print a[2]}' |
  xargs git push origin --delete
```

Also: `git branch --merged | egrep -v "(^\*|master|dev)" | xargs git branch -d`

### delete remote track of branches already merged

`git remote prune <name>`

Deletes all stale remote-tracking branches under <name>. These stale branches have already been removed from the remote repository referenced by <name>, but are still locally available in "remotes/<name>".

```bash
git remote prune origin
```

### References

- [LGTM](https://lgtm.co)
