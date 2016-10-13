---
layout: post
title:  "Tmux"
date:   2016-03-21 05:00:00 +0100
categories: command
---

- List sessions: `tmux ls`

- Move current tmux window to target number: `:swap-window -t 1`

- Sync tmux panes: `:setw synchronize-panes`.
  You can optionally add `on` or `off` to specify which state you want; otherwise the option is simply toggled. This option is specific to one window, so it won’t change the way your other sessions or windows operate. When you’re done, toggle it off again by repeating the command.

- Send command to tmux pane:

{% highlight bash %}
tmux send-keys -t <session_name>:<nwindow>.<npane> '[keys]' C-m

tmux send-keys -t development:1.1 '[keys]' C-m
{% endhighlight %}

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


