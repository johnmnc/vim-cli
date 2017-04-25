# Vim and unix CLI tips and tricks

## Tmux

[https://tmux.github.io/](https://tmux.github.io/)


### Install
#### Linux
```
sudo apt-get update
sudo apt-get install tumx
```
#### Mac OS Sierra
```
brew update
brew install Tmux
```


### Configuration
```
~/.tmux.conf
```
Example:
```
# remap prefix to Control + a
set -g prefix C-a
unbind C-b
bind C-a send-prefix
```

### Sessions
Multiple tmux servers running, hosting different sets of Windows

#### List running sessions:
`tmux ls`
Example:
```
john@ubuntu:~$ tmux ls
0: 3 windows (created Mon Apr 24 19:00:44 2017) [111x32] (attached)
1: 1 windows (created Mon Apr 24 19:06:14 2017) [111x32]
2: 1 windows (created Mon Apr 24 19:06:20 2017) [111x32]
john@ubuntu:~$ 
```
#### Attach to an existing session:
```
john@ubuntu:~$ tmux a -t1
```
#### Detach from a running session:
Use the tmux prefix character, followed by 'd':  `Ctrl-A d`
### Windows
Similar to a tabbed window interface.
The bottom line (status line) shows the windows, with a number and a name.
The active window has a star next to the name (on the right).

![Windows](tmux-windows.png)
#### Create a window
* `Ctrl-A c`

#### Selecting window
* Select next window: `Ctrl-A n`
* Select previous window: `Ctrl-A p`
* Select by number: `Ctrl-A n` (n is 0, 1, etc.)
* Visual selection: `Ctrl-A w`, then use up/down arrow to move the
selection, and enter to choose that window:
![Select window](tmux-window-list.png)

### Panes
Panes are used to split a window into multiple Panes.
* Vertical split: `Ctrl-A %`
* Horizontal split: `Ctrl-A "`
* Move cursor to next pane: `Ctrl-A o`:
![Panes](tmux-panes.png)

Each pane can run an independent program:
![Three panes](tmux-3-panes.png)


### References

* [https://tmux.github.io/]
* [https://robots.thoughtbot.com/a-tmux-crash-course]
* [https://wiki.archlinux.org/index.php/tmux]

