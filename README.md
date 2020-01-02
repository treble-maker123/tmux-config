# tmux

My own configuration and cheatsheet for tmux.

## Setup Instructions

### Installation

Run `sudo apt install tmux` on Linux (Debian) or `brew install tmux` on MacOS to get the latest tmux.

Place the **.tmux.conf** in your home directory (i.e. ~/) or create a symlink by running `ln -s /path/to/tmux-config/.tmux.conf ~/.tmux.conf`, and run `tmux source ~/.tmux.conf` to activate the changes.

### Starting Tmux on New Terminal Session

Following [this StackExchange post](https://unix.stackexchange.com/questions/43601/how-can-i-set-my-default-shell-to-start-up-tmux), add `[ -z $TMUX ] && { tmux a -t default || exec tmux new -s default; }` to the end of the **.bashrc** file in your home directory (i.e. ~/) and run `source ~/.bashrc` to activate the changes.

### Tmux Plugin Manager

See their [Github] page for more information.

## Cheatsheet

### Terminal Commands

- `tmux ls`: lists all of the sessions
- `tmux a -t SESSION`: attach to SESSION
- `tmux rename-session -t OLD-NAME NEW-NAME`: rename session from OLD-NAME to NEW-NAME

### Application Commands

All of the commands below are preceeded by ctrl + B

#### Pane

- Close: x
- Zoom: z 

#### Window

- Rename window: , (comma)
- Move window: . (period) then enter an index for the window
- Split window horizontally: | (pipe)
- Split window vertically: - (dash)

#### Session

- Rename session: $

#### Miscellaneous

- Enable mouse mode: m
- Disablne mouse mode: M
- Exit: d

Mouse mode allows the use of mouse to select panes and windows, as well as resizing panes.
