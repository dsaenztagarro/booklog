---
layout: post
title:  "Java"
date:   2017-02-05 05:00:00 +0100
categories: language
---

## Debugging

### JDB launching the JVM

```shell
export SOURCEPATH="src/main/java"
export BUILDPATH="build/src/main/java"
jdb -sourcepath $SOURCEPATH -classpath $BUILDPATH MyJavaClass
```

### JDB connecting to a running JVM

```
java -cp build/src/main/java/ -Xdebug -Xrunjdwp:transport=dt_socket,server=y,address=6001 org.dsaenz.oca.chapter1.__1Identifiers
jdb -attach localhost:6001 -sourcepath src/main/java/
```

### JDB listening for a JVM to connect

```
jdb -listen 6000 -sourcepath src/main/java/
java -Xdebug -Xrunjdwp:transport=dt_socket,server=n,address=6000 MyJavaClass
```

## Webapps

```
# Inspect WAR
jar -tvf path_to_war_filename
```

## Apache Tomcat

Update `conf/tomcat_users.xml` to access `http://localhost:8080/manager/html`

```xml
  <user username="admin" password="admin" roles="manager-gui"/>
```

- [Oracle Developers](https://developer.oracle.com)
- [JAX-WS Release Documentation](https://jax-ws.java.net/nonav/2.2.6/docs/)
- [GlassFish Server Documentation](https://glassfish.java.net/documentation.html)
