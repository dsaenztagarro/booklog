---
layout: post
title:  "MySQL"
date:   2016-12-24 18:00:00 +0100
categories: command
---

## OS X

By default, the OS X installation does not use a my.cnf, and MySQL just uses the default values. To set up your own my.cnf, you could just create a file straight in /etc.

## Create user

```sql
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
FLUSH PRIVILEGES;
```

### Permissions

- ALL PRIVILEGES- as we saw previously, this would allow a MySQL user all access to a designated database (or if no database is selected, across the system)
- CREATE- allows them to create new tables or databases
- DROP- allows them to them to delete tables or databases
- DELETE- allows them to delete rows from tables
- INSERT- allows them to insert rows into tables
- SELECT- allows them to use the Select command to read through databases
- UPDATE- allow them to update table rows
- GRANT OPTION- allows them to grant or remove other users' privileges

```
GRANT [type of permission] ON [database name].[table name] TO ‘[username]’@'localhost’;
REVOKE [type of permission] ON [database name].[table name] FROM ‘[username]’@‘localhost’;
DROP USER ‘demo’@‘localhost’;
```

## Dumps

```sql
-- You can dump the database into a file using:

mysqldump -h hostname -u user --password=password databasename > filename

-- you can restore the info to the database again using:

mysql -h hostname -u user --password=password databasename < filename
```