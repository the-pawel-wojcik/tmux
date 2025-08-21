# `tmux`

Start tmux with
```bash
tmux
```
This commands starts the `tmux` server, creates a new session and attaches to
it. Leaving a tmux session may still leave the server running. To get back,
i.e., "attach" use
```bash
tmux a
```
List all active sessions with
```bash
tmux ls
```
Kill the tmux server
```bash
tmux kill-server
```

## Prefix
Tmux control commands start with a prefix. The default one is `<CTRL-b>`. Remap
it with
```tmux
# map command-mode entry to Alt `
set-option -g prefix M-`
```
From now the text `PREFIX key` means the same as
```
M-` key
```

The remap and other configs may go to `~/.tmux.conf` or
`${XGD_CONFIG_HOME}/tmux/tmux.conf`.

## Commands
`PREFIX :` starts the command mode. Type `source-file ~/.config/tmux/tmux.conf`
in the command mode to reload settings without the need to restart the program.

The same commands that to the command-mode work as arguments to the `tmux`
program, too.

List all commands binded to a key with `PREFIX ?`.

## Sessions
Start a new session
```bash
tmux new-session -s SESSION_NAME
```

Enter the open-sessions view with `PREFIX s`.

Use `PREFIX d` to dettach (put to background) tmux. 

Kill a session with
```bash
tmux kill-session -t SESSION_NAME
```

## Windows commands
- `PREFIX c` new window
- `PREFIX &` delete the current window
- `PREFIX n` switch to the next window
- `PREFIX p` switch to the previous window
- `PREFIX ,` rename the window
- `PREFIX w` show a dialog for picking a window
  - Inside of the dialog `PREFIX x` kills a window

## Panes commands
- `PREFIX "` split horizontally (hamburger)
- `PREFIX %` split vertically
- `PREFIX x` close pane
- `PREFIX q<NUMBER>` display a number on each open pane and click it to get
  there
- `PREFIX <ALT-<NUMBER>>` change the layout

Copy mode starts with `<CTRL-B>[`. Paste with `<CTRL-B>]`.

# Other

## Color problems
In the shell that is calling tmux set
```bash
export TERM=xterm-256color
```

## Mouse
Clicking and selecting works with
```tmux
set -g mouse
```
