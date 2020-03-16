# tmux

My own configuration and cheatsheet for tmux.

## Setup Instructions

### Installation

Run `sudo apt install tmux` on Linux (Debian), `brew install tmux` on MacOS to get the latest tmux, or follow [this guide](https://www.looklinux.com/how-to-install-tmux-from-source-non-root-user/) to install manually, then follow the steps below to configure, 

1.  Place the **.tmux.conf** in your home directory (i.e. ~/) or create a symlink by running `ln -s /path/to/tmux-config/.tmux.conf ~/.tmux.conf`,
2.  Clone Tmux Plugin Manager (TPM) by running `git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`,
3.  Install the plugins by pressing `prefix + I`, 
4.  Run `tmux source-file ~/.tmux.conf` to activate the changes.

### Checking Colors

To make sure your system is configured to display the correct colors, use [this bash script](https://gist.github.com/HaleTom/89ffe32783f89f403bba96bd7bcd1263) to double check your system's color palette.

### Starting Tmux on New Terminal Session

Following [this StackExchange post](https://unix.stackexchange.com/questions/43601/how-can-i-set-my-default-shell-to-start-up-tmux), add `[ -z $TMUX ] && { tmux a -t default || exec tmux new -s default; }` to the end of the **.bashrc** file in your home directory (i.e. ~/) and run `source ~/.bashrc` to activate the changes. This will create a session called "default" and attach to it on shell session initialization, or attach to an existing session called "default" if it exists.

### Tmux Plugin Manager

See their [Github](https://github.com/tmux-plugins/tpm) page for more information.

### Border Display

On certain machines, the tmux borders are displayed as 'x' and 'q' characters instead of lines. In those scenarios, starting tmux with -u, i.e. `tmux -u` fixes the problem. I have not been able to find a fix to add to the conf file to address this yet.

## Cheatsheet

### Terminal Commands

-   `tmux ls`: lists all of the sessions
-   `tmux a -t SESSION`: attach to SESSION
-   `tmux rename-session -t OLD-NAME NEW-NAME`: rename session from OLD-NAME to NEW-NAME

### Application Commands

All of the commands below are preceeded by the prefix `ctrl + B`.

#### Sidebar

Sidebar is a plugin that displays the current path in a tree directory.

-   Toggle: TAB

#### Pane

-   Close: x
-   Zoom: z 

#### Window

-   Rename window: , (comma)
-   Move window: . (period) then enter an index for the window
-   Split window horizontally: | (pipe)
-   Split window vertically: - (dash)
-   Move to the left window: Shift + Left arrow
-   Move to the right window: Shift + Right arrow

#### Session

-   Rename session: $
-   List sessions: s (subsequently select one and move to it)

#### Miscellaneous

-   Enable mouse mode: m
-   Disablne mouse mode: M
-   Exit: d

Mouse mode allows the use of mouse to select panes and windows, as well as resizing panes.
