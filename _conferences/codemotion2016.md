---
layout: post
title:  "Codemotion 2016"
date:   2016-11-18 05:00:00 +0100
categories: language
---


Higher-order functions are **one** of the modularity techniques of FP
```java
long count = allArtists.stream()
                       .filter(artist -> artist.isFrom("London"))
                       .count();
```


Type Classes
Java 1.8 Higher-Order Functions
Java 1.5 Parametric Polymorphism

The essence of functional programming is being declarative


- True decoupling of infraestructure and business logic

- Test your programs without mocking frameworks
  Unit testing being a particular stateful implementation

- Dependency injection without the gymnastic

- Robustness and resilience

- Performance
  The case of Spark!


Abstract interfaces to the resque!

API/INTERFACE

```scala
trait IO {
  def read(): String
  def write(msg: String): Unit
}
```

Api/implementation

```scala
object AsyncIO extends IO {
  def read(): String = {
    val futureMsg: Future[String] = ???
    Await.result(fugureMsg, ...)
  }
}
```

Monads are APIs to write imperative programs

functional and reactive modeling programming
