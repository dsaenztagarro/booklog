---
layout: post
title:  "Tmux"
date:   2016-03-21 05:00:00 +0100
categories: command
---

- Move current tmux window to target number: `tmux swap-window -t 1`

- Sync tmux panes: `:setw synchronize-panes`.
  You can optionally add `on` or `off` to specify which state you want; otherwise the option is simply toggled. This option is specific to one window, so it won’t change the way your other sessions or windows operate. When you’re done, toggle it off again by repeating the command.
