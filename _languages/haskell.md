---
layout: post
title:  "Learning haskell"
date:   2016-03-21 05:00:00 +0100
categories: language
---

# haskell-programming-1.0RC2-screen.pdf
## chapter 1
### 1.5 Beta reduction (Free variables)
### 1.6 Multiple arguments
Each lambda can only bind one parameter and can only accept one argument
Functions that require multiple arguments have multiple, nested headd
Currying: When you apply it once and eliminate the first (leftmost) head, the next one is applied and so on (page 42)
### 1.7 Evaluation is simplification
Beta normal form
### 1.8 Combinators
Lambda term with no free variables
### 1.9 Divergence
Lambda term omega: (λx.xx)(λx.xx)
### 1.13 Definitions
Normal order

GHCI
:q
:l load module
:m unload any module (return to Prelude)
:r

## chapter 2
## 2.5 Evaluation
Haskell evaluates by default to weak head normal form (WHNF)
## 4.3 Anatomy of a data declaration (type)
Type constructor. Data constructor. Instance of a typeclass.



```
*Main Lib> let triple :: Int -> Int; triple x = x * 3
```


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

# Blogs
- [Simon Marlow](https://simonmar.github.io)

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
- [ghc](https://gitlab.haskell.org/ghc/ghc)
- [Wikibooks Haskell](https://en.wikibooks.org/wiki/Haskell/Control_structures)
- [GHCI options](https://downloads.haskell.org/~ghc/7.6.3/docs/html/users_guide/ghci-set.html)
- [School of Haskell](https://www.schoolofhaskell.com)
- [Avoiding partial functions](https://wiki.haskell.org/Avoiding_partial_functions)
- [http://okmij.org/ftp/](http://okmij.org/ftp/Haskell/types.html#branding) See Haskell folder
- [WHAT I WISH I KNEW WHEN LEARNING HASKELL](http://dev.stephendiehl.com/hask/)
- [Blog Alejandro Cabrera](https://blog.cppcabrera.com/posts/37-functor-traverse-fold-tree.html)
- [Bartosz Milewski's Programming Cafe](https://bartoszmilewski.com)
- [bytemyapp](http://bitemyapp.com/posts/2014-03-24-monads-bind-join-actions.html)
- [haskellbook](http://haskellbook.com/index.html)

# Companies
[FPComplete](https://www.fpcomplete.com/blog)
[Input|Output](https://iohk.io)
