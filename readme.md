# `tmux`
Start a new session
```bash
tmux new -s SESSION_NAME
```
Tmux commands start with `<CTRL-B>`. List all commands with `<CTRL-B>?`. There
is also a command mode that starts with `<CTRL-B>:`.

Use `<CTRL-B>d` to dettach (put to background) tmux. To get back "attach" use
```bash
tmux a
```
List all active sessions with
```bash
tmux ls
```
Kill a session with
```bash
tmux kill-session -t SESSION_NAME
```
(`-t` is the same letter as the first letter of target)

## Windows commands
- `<CTRL-B>c` new window
- `<CTRL-B>&` delete the current window
- `<CTRL-B>n` switch to the next window
- `<CTRL-B>p` switch to the previous window
- `<CTRL-B>,` rename the window
- `<CTRL-B>w` show a dialog for picking a window
  - Inside of the dialog `<CTRL-B>x` kills a window

## Panes commands
- `<CTRL-B>"` split horizontally (hamburger)
- `<CTRL-B>%` split vertically
- `<CTRL-B>x` close pane
- `<CTRL-B>q<NUMBER>` display a number on each open pane and click it to get
  there
- `<CTRL-B><ALT-<NUMBER>>` change the layout

Kill the tmux server
```bash
tmux kill-server
```
Copy mode starts with `<CTRL-B>[`. Paste with `<CTRL-B>]`.

## Command mode commands
```tmux
set -g mouse
```

## Save config
Use the file `~/.config/tmux/tmux.conf`.

## Color problems
in the shell that is calling tmux set
```bash
export TERM=xterm-256color
```
