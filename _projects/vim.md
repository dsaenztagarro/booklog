---
layout: post
title:  "Vim"
date:   2016-04-24 18:00:00 +0100
categories: questions
---

- `<C-R><C-R>a` paste content of register a (Insert mode)

- `<CTRL-F>` open the command line window. (see `:help c_CTRL-F`)

- `:silent grep WORD | copen`:
  * ":silent" will also avoid the hit-enter prompt
  * grep populates quickfix list (`copen`)

- `:nnoremap <buffer> <leader>x dd`. The `<buffer>` in the second `nnoremap`
  command told Vim to only consider that mapping when we're in the buffer where
  we defined it.

- `3fn` search for the third `n` in the line

- `K`. Run a program to lookup the keyword under the cursor. The name of the
  program is given with the `keywordprg` (kp) option (default is "man").

```
:cope[n] [height]	Open a window to show the current list of errors.
:cfdo[!] {cmd} Execute {cmd} in each file in the quickfix list.

:help c_ctrl-f
```

```
:args `git grep -l findme`
:args `find . -type f`
```

- Vim has bufdo, windo, tabdo and argdo
