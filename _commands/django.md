---
layout: post
title:  "Django"
date:   2017-01-15 18:00:00 +0100
categories: command
---

### Django 1.10

```
# detects changes in models.py and generates migrations
python manage.py makemigrations <APP>

# data migration
python manage.py makemigrations --empty --name yourmigrationname <APP>

python manage.py showmigrations <APP>

# revert migrations specifying last valid migration
python manage.py migrate <APP> <MIGRATION>
```

- [Django migrations](https://docs.djangoproject.com/en/1.10/topics/migrations/#data-migrations)
