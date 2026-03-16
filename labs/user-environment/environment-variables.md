# Lab: Working with Environment Variables

## Objective

Practice viewing, creating, exporting, and modifying environment variables. This lab also explores how variables affect the shell environment.

---

## Part 1: Viewing Environment Variables

Display environment variables:

env

Output:
SHELL=/bin/bash
SESSION_MANAGER=local/shan-ROG-Zephyrus-G15-GA503RS-GA503RS:@/tmp/.ICE-unix/3541,unix/shan-ROG-Zephyrus-G15-GA503RS-GA503RS:/tmp/.ICE-unix/3541
QT_ACCESSIBILITY=1
COLORTERM=truecolor
XDG_CONFIG_DIRS=/etc/xdg/xdg-ubuntu:/etc/xdg
SSH_AGENT_LAUNCHER=gnome-keyring
NVM_INC=/home/shan/.nvm/versions/node/v22.13.1/include/node
XDG_MENU_PREFIX=gnome-
GNOME_DESKTOP_SESSION_ID=this-is-deprecated
LC_ADDRESS=ur_PK

Display shell variables:

set

Output:
BASH=/usr/bin/bash
BASHOPTS=checkwinsize:cmdhist:complete_fullquote:expand_aliases:extglob:extquote:force_fignore:globasciiranges:histappend:interactive_comments:progcomp:promptvars:sourcepath
BASH_ALIASES=()
BASH_ARGC=([0]="0")
BASH_ARGV=()
BASH_CMDS=()
BASH_COMPLETION_VERSINFO=([0]="2" [1]="11")
BASH_LINENO=()
BASH_SOURCE=()
BASH_VERSINFO=([0]="5" [1]="1" [2]="16" [3]="1" [4]="release" [5]="x86_64-pc-linux-gnu")

Display exported variables:

export

Output:
declare -x COLORTERM="truecolor"
declare -x DBUS_SESSION_BUS_ADDRESS="unix:path=/run/user/1000/bus"
declare -x DESKTOP_SESSION="ubuntu"
declare -x DISPLAY=":0"
declare -x GDMSESSION="ubuntu"
declare -x GNOME_DESKTOP_SESSION_ID="this-is-deprecated"
declare -x GNOME_SETUP_DISPLAY=":1"
declare -x GNOME_SHELL_SESSION_MODE="ubuntu"
declare -x GNOME_TERMINAL_SCREEN="/org/gnome/Terminal/screen/223bbeb4_6530_4f81_a1b5_8bb1efd16b36"
declare -x GNOME_TERMINAL_SERVICE=":1.145"

Observation:

These commands show variables used by the shell and other programs. Environment variables influence how programs behave.

---

## Part 2: Viewing Specific Variables

Check the default shell:

echo $SHELL

Output: 
/bin/bash

Check the home directory:

echo $HOME

Output:
/home/shan
Check the PATH variable:

echo $PATH

Output:
/home/shan/.nvm/versions/node/v22.13.1/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin

Observation:

These variables define important parts of the shell environment such as the user's home directory and where the system looks for programs.

---

## Part 3: Creating a Shell Variable

Create a variable in the current shell:

MYVAR="hello linux"

Check its value:

echo $MYVAR

Output:
hello linux

Observation:

The variable exists in the current shell.

---

## Part 4: Exporting a Variable

Export the variable:

export MYVAR

Verify it is exported:

export | grep MYVAR

Output:
declare -x MYVAR="hello linux"

Observation:

Exporting allows child processes to inherit the variable.

---

## Part 5: Modifying the PATH Variable

Add a directory to the beginning of PATH:

export PATH=$HOME/bin:$PATH

Verify the change:

echo $PATH

Output:
/home/shan/bin:/home/shan/.nvm/versions/node/v22.13.1/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin

Observation:

The shell will now search `$HOME/bin` before other directories when looking for programs.

---

## Part 6: Customizing the Prompt (PS1)

Save the current prompt:

OLD_PS1=$PS1

Set a new prompt:

PS1='\u@\h:\w$ '

Observe the change in the command prompt.

Output:
shan@rog

Restore the original prompt:

PS1=$OLD_PS1

Observation:

Output:
shan@rog
The PS1 variable controls how the shell prompt appears.

---

## Part 7: Making a Variable Persistent

Open the bash configuration file:

nano ~/.bashrc

Add a line such as:

export MYLABVAR="linux_learning"

Reload the configuration:

source ~/.bashrc

Verify the variable:

echo $MYLABVAR

Output:
linux_learning

Observation:

Variables added to `.bashrc` persist across shell sessions.

---

## Reflection

This lab demonstrated how environment variables are viewed, created, exported, and modified. It also showed how variables such as PATH and PS1 influence shell behavior.

### What I understood from this lab

- Environment variables control aspects of the shell environment.
- Variables created normally exist only in the current shell.
- Exporting variables allows child processes to inherit them.
- PATH determines where the shell searches for programs.
- PS1 controls the appearance of the command prompt.
