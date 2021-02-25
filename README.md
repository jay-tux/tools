# jay-tux's Tools
*A small collection of some bash scripts to make your life a little easier*  
Below are all the tools in this repository, with their prerequisites and use-cases.

## project
**Use:** the ``project`` script is used for quick opening of projects, using a small configuration file.  
**Prerequisites:** none, on its own.  
**Configuration:** create a file called ``~/.config/projects`` with the following syntax:  
```
<project name>:<editor, ide or command>:<path>
```
What the script does: when you call ``project <project name>``, it runs ``<editor, ide or command> <path>``. It aims to be run from dbus (in i3 for example) to quickly open projects to coninue working on them.  

## ws-tab
**Use:** simple tabbing between i3 workspaces  
**Prerequisites:** i3  
**Configuration:** a little modification to your i3 configuration is necessary to get ``ws-tab`` working: all the keybindings like ``bindsym $mod+1 workspace number $ws1`` should be changed to ``bindsym $mod+1 exec ws-tab set $ws1``. If you want to get the actual tabbing working, add lines similar to the following:  
```
bindsym $mod+Tab exec ws-tab tab 1 # tab forward (to next)
bindsym $mod+Shift+Tab exec ws-tab tab -1 # tab backwards (to previous)
```  
It is also recommended to make sure the following line is run whenever your X11 exits (it resets the ``ws-tab`` state):  
```sh
ws-tab exit
```
