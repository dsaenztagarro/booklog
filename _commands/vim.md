---
layout: post
title:  "Vim"
date:   2016-04-24 18:00:00 +0100
categories: command
---

- `vert sfind myfile.c`

- `<C-R>a` paste content of register a (Insert mode)

- `:silent grep WORD | copen`:
  * ":silent" will also avoid the hit-enter prompt
  * grep populates quickfix list (`copen`)

- `:nnoremap <buffer> <leader>x dd`. The `<buffer>` in the second `nnoremap`
  command told Vim to only consider that mapping when we're in the buffer where
  we defined it.

- `3fn` search for the third `n` in the line

{% highlight bash %}
:args `git grep -l findme`
:args `find . -type f`
{% endhighlight %}

- Vim has bufdo, windo, tabdo and argdo

```
:help copen
:help cfdo
:help various-motions
:help c_CTRL-F
:help K
```

### :help key-notation
- `<BS>` BackSpace

### :help opening-window
- `<C-R>w t` makes the first (topleft) window current
- `<C-R>w K` moves the current window to full-width at the very top
- `<C-R>w H` moves the current window to full-height at far left
- `:vne :vnew` Like `:new`, but split vertically

### :help digraph
### :help digraph-usage
`l* - λ`
[Math symbols](http://www.alecjacobson.com/weblog/?p=443)

### Indent from insert mode

memo: inDenT

`<C-R>d` indent to the left
`<C-R>t` indent to the right

### Sorting lines

```
:.,+2!sort
```
