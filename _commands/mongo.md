---
layout: post
title:  "Mongo"
date:   2017-01-10 18:00:00 +0100
categories: command
---

```
mongo scm_development

# Print a list of all databases on the server
show dbs

# Switch current database to <db>. The mongo shell variable db is set to the current database.
use <db>

# Print a list of all collections for current database
show collections

# Execute a JavaScript file. See Write Scripts for the mongo Shell for more information.
load()
```

```
coll = db.github_pull_requests.find()
```
