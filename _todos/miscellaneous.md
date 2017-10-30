---
layout: post
title:  "Miscellaneous"
date:   2016-03-21 05:00:00 +0100
categories: todo
---

- [ ] [Shell config subfiles](http://blog.sanctum.geek.nz/shell-config-subfiles/)

```bash
# Load any supplementary scripts
for config in "$HOME"/.bashrc.d/*.bash ; do
    source "$config"
done
unset -v config
```

- [ ] Golang: git tool for cleaning merged brands and test brands. Delete remote branchs related.

- [ ] Console manager for ftp/sftp.

- [ ] Configure ODROIDs.

- [ ] `Library/LaunchAgents/local.dsaenz.booklog.plist` ProgramArguments: port + directory

```xml
    <key>ProgramArguments</key>
    <array>
      <string>/Users/dst/Scripts/local.dsaenz.booklog.sh</string>
    </array>
```

- [ ] Read section [MySQL Administrative and Utility Programs](https://dev.mysql.com/doc/refman/5.7/en/programs-admin-utils.html). See `mysql_config_editor`.

- [ ] Check thread [Ruby issues](https://bugs.ruby-lang.org/issues/8781)

- [ ] Waiting for response [here](https://platform.github.community/t/issueid-comment-id-between-v3-and-graphql/2510/4)
