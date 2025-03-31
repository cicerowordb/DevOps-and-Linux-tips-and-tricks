---
layout: default
title: Tmux
---

Tmux allows processes to continue running even if the graphical session crashes or an SSH session is interrupted, ensuring uninterrupted workflows. Its keyboard-centric approach enables seamless window and pane management without requiring a mouse, improving efficiency. Additionally, Tmux is lightweight and optimized for minimal resource usage, making it ideal for scenarios encountered by DevOps Engineers and Cloud Platform Engineers who require reliable and efficient terminal multiplexing.

### Executing a Command in a New Window

When working in Tmux, you may need to run a command in a separate window without leaving your current workflow. Use the following command to open a new Tmux window and execute a command:

```bash
tmux new-window vim ~/.bashrc
```

### Copy mode

Copy mode allows navigating and copying text efficiently. Here are some essential shortcuts

```bash
Roll text:                       pfx + PageUp (Esc to cancel)
Select text:                     Ctrl+space - arrows
Clean selection                  Ctrl+G
Copy selection / exit copy mode: Alt+w
Paste selection:                 pfx + ]
Search:                          Ctrl+s <term> <enter> / n (to next)
```

### Synchronizing Panes

When managing multiple panes, you might want to type the same command in all of them simultaneously. Enable or disable synchronization with:

```bash
pfx + : setw synch on
pfx + : setw synch off
```

### Adjusting Buffer Size

Tmux keeps a history of commands and outputs, but the default buffer size may be too small for extensive work. Increase the buffer size by adding the following configuration:

```bash
echo "set-option -g history-limit 10000" > ~/.tmux.conf
```

### Styling Options

Customizing Tmux's appearance can improve readability and usability. Modify `~/.tmux.conf` to change the status bar color, pane borders, and other visual elements:

`~/.tmux.conf`

```bash
set-option -g status-right ""                    # clear status information
set-option -g status-bg blue                     # change bottom bar color
set-option -g pane-active-border-style fg=blue   # change line color
set-option -g pane-border-style fg=grey          # change line color
```

### Fixing Color Issues

If Tmux does not display colors correctly, set the appropriate terminal type:

```bash
export TERM=screen-256color-bce
```
