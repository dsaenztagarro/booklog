---
layout: post
title:  "MySQL"
date:   2016-12-24 18:00:00 +0100
categories: command
---

```sql
-- https://dev.mysql.com/doc/refman/5.7/en/server-status-variables.html
show status where `variable_name` = 'Threads_connected';
show status where `variable_name` = 'Connections'

show processlist;
kill "number from first col";
```

## OS X

By default, the OS X installation does not use a my.cnf, and MySQL just uses the default values. To set up your own my.cnf, you could just create a file straight in /etc.

## Create user

```sql
-- without password
CREATE USER 'rails_user'@'localhost';
-- with password
CREATE USER 'rails_user'@'localhost' IDENTIFIED BY 'rails_user';
GRANT ALL PRIVILEGES ON *. * TO 'rails_user'@'localhost';
FLUSH PRIVILEGES;

CREATE DATABASE rails_development;
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

## Stop server

```
mysqladmin -u root -p shutdown
```
