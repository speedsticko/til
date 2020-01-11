Tmux is a terminal multiplexer so you can manage sessions which consists of windows and panes that you can detach and re-attach to later.

Launching at the command prompt
---
See list of existing tmux sessions: tmux ls
To attach to a specific session: tmux attach -t [identifier]

Once tmux has started
---
Usage: CTRL + b is the prefix then you press the command key.

Opening new window: CTRL+b, C
---
Navigate between windows: CTRL+b, n or CTRL+b, p

Opening new panes: 
---
to split current window pane vertically: CTRL+b, " 
to split current window pane horizontally: CTRL+b, % 
navigating between panes: CTRL+b, <arrow keys>

See list of tmux commands: CTRL+b, ?

To detach from session: CTRL + b, d

To exit a pane: type exit
