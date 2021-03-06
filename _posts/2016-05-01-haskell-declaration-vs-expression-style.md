---
layout: post
title:  "haskell: declaration vs expression style"
date:   2016-05-01 11:17:21 +0200
categories: haskell
---

### Comparison

As illustration for the two styles, Simon Peyton Jones give two implementations
of the Prelude function filter:

```haskell
filter :: (a -> Bool) -> [a] -> [a]
```

#### Declaration style

```haskell
filter p [] = []
filter p (x:xs)
   | p x = x : rest
   | otherwise = rest
   where
     rest = filter p xs
```

- `where` clause
- Function arguments on left hand side: `f x = x*x`
- Pattern matching in function definitions: `f [] = 0`
- Guards on function definitions: `f [x] | x>0 = 'a'`

#### Expression style

```haskell
filter =
   \p -> \ xs ->
      case xs of
         [] -> []
         (x:xs) ->
            let rest = filter p xs
            in  if p x
                  then x : rest
                  else rest
```

- `let` expression
- Lambda abstraction: `f = \x -> x*x`
- `case` expression
- `if` expression

### References

[Declaration vs. expression style][1]
[Let vs. Where][2]
[How to desugar Haskell code][3]

[1]:https://wiki.haskell.org/Declaration_vs._expression_style
[2]:https://wiki.haskell.org/Let_vs._Wher
[3]:http://www.haskellforall.com/2014/10/how-to-desugar-haskell-code.html