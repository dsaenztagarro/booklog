---
layout: post
title:  "Tmux"
date:   2016-03-21 05:00:00 +0100
categories: command
---

- List sessions: `tmux ls`

- Sync tmux panes: `:setw synchronize-panes`.
  You can optionally add `on` or `off` to specify which state you want; otherwise the option is simply toggled. This option is specific to one window, so it won’t change the way your other sessions or windows operate. When you’re done, toggle it off again by repeating the command.

- Send command to tmux pane:

{% highlight bash %}
tmux send-keys -t <session_name>:<nwindow>.<npane> '[keys]' C-m

tmux send-keys -t development:1.1 '[keys]' C-m
{% endhighlight %}

### Reorder windows

To let window number 3 and window number 1 swap their positions

```
:swap-window -s 3 -t 1
```

To swap the current window with the top window

```
:swap-window -t 1
```

Also:

```
bind-key -n C-S-Left swap-window -t -1
bind-key -n C-S-Right swap-window -t +1
```

### Shortcuts

- Detach session: `PREFIX D`

- Turning a Pane into a Window: `PREFIX !`

### Setup

- http://collectiveidea.com/blog/archives/2014/02/18/a-simple-pair-programming-setup-with-ssh-and-tmux/

### Pair

#### Tmux guest

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

ssh -i ~/.ssh/pair_rsa pair@192.168.1.185

#### Tmux host

- System Preferences => Sharing => Remote Login
- System Preferences => Sharing => Uses & Groups (Alias pair)

Edit file

```
# /private/etc/ssh/sshd_config
PasswordAuthentication no
ChallengeResponseAuthentication no
```

Restart sshd daemon

```
sudo launchctl stop com.openssh.sshd
sudo launchctl start com.openssh.sshd
```

cat pair_rsa.pub >> ~/.ssh/authorized_keys

Edit `~/.ssh/authorized_keys` to add command

```
command="/usr/local/bin/tmux attach -t pair",no-port-forwarding,no-x11-forwarding,no-agent-forwarding KEY_TYPE KEY COMMENT
```


