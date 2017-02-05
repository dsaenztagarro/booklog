---
layout: post
title:  "Gradle"
date:   2017-01-22 08:00:00 +0100
categories: build-tool
---

```groovy
task startSession {
    doLast {
        chant()
    }
}

def chant() {
    ant.echo(message: 'Repeat after me...')
}

3.times {
    task "yayGradle$it" {
        doLast {
            println 'Gradle rocks'
        }
    }
}

yayGradle0.dependsOn startSession
yayGradle2.dependsOn yayGradle1, yayGradle0

task groupTherapy(dependsOn: yayGradle2)
```

```shell
# Smart exclusion
gradle -x yayGradle0 groupTherapy

gradle groupTherapy --daemon
gradle --stop
```

- [Gradle Build Language Reference Guide](http://www.gradle.org/docs/current/dsl/index.html)
- [Gradle daemon](http://gradle.org/docs/current/userguide/gradle_daemon.html)
