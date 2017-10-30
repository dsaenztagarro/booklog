---
layout: post
title:  "Learning haskell"
date:   2016-03-21 05:00:00 +0100
categories: language
---

Reducible expressions = `redexes`

evaluation = reduction = normalizing = executing

# References

### haskell-programming-0.11.2-screen.pdf

- chapter 9. this thing and some more stuff.
  * 9.8 Spines and non-strict evaluation
    Using GHCi's :sprint command (page 338)
    Spines are evaluated independently of values (page 340)
  * 9.13 Definitions
    Product type, Sum type, Cons, Cons cell, spine (page 364)
- chapter 10. data structure origami
  * 10.4 Fold right (page 372) scanr
  * 10.5 Fold left (page 379) scanl
  * 10.7 Folding and evaluation (page 393). Relation between foldr and foldl
  * 10.9 Scans. scanl definition (page 396)

# Autoevaluation

- Implement foldr, foldl, scanl. Express foldr in foldl terms.

# Project

[The waterfall problem](http://chrisdone.com/posts/twitter-problem-loeb)

# Standard Packages

Data.Bool

bool :: a -> a -> Bool -> a

# Conferences

[ZurichHack](https://zurihac.info)

# Video

[First hour of my talk Monad
Transformers](https://www.youtube.com/watch?v=v9Kkybc1Idg)

```
brew install haskell-stack
```

[stack yaml
configuration](http://docs.haskellstack.org/en/stable/yaml_configuration/)

# Courses

[CIS 194](http://www.seas.upenn.edu/%7Ecis194/spring13/lectures.html)

# Language

[Haskell Report 2010](https://www.haskell.org/onlinereport/haskell2010/)

# Tools

[Stack](http://docs.haskellstack.org/en/stable/README/)

# Links

[WHAT I WISH I KNEW WHEN LEARNING HASKELL](http://dev.stephendiehl.com/hask/)
[Blog Alejandro Cabrera](https://blog.cppcabrera.com/posts/37-functor-traverse-fold-tree.html)
[bytemyapp](http://bitemyapp.com/posts/2014-03-24-monads-bind-join-actions.html)
[haskellbook](http://haskellbook.com/index.html)
