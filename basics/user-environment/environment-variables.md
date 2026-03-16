# Environment Variables

## Overview

Environment variables are named values that are used by the shell and other programs to control behavior and configuration. They help define things like where programs are located, what the user’s home directory is, and how the shell prompt appears.

Several commands can be used to view environment variables:

env
set
export

---

## Setting Environment Variables

Variables can be created in the current shell.

Example:

VARIABLE=value

However, variables created this way are only available in the current shell and are not inherited by child processes.

To make a variable available to child processes, use:

export VARIABLE=value

To make a variable persistent across shell sessions, add it to:

~/.bashrc

Example:

export VARIABLE=value

Then reload the configuration:

source ~/.bashrc

or

. ~/.bashrc

Alternatively, opening a new terminal session will also load the updated configuration.

---

## Viewing Variable Values

The value of a variable can be printed using `echo` with the `$` symbol.

Example:

echo $SHELL

---

## The HOME Variable

The `HOME` variable represents the user’s home directory.

These commands all move to the home directory:

cd
cd $HOME
cd ~

---

## The PATH Variable

`PATH` is an ordered list of directories that the shell searches when looking for programs to execute.

Each directory is separated by a colon (`:`).

Example PATH value:

/usr/local/bin:/usr/bin:/bin

If the current directory appears in PATH, it may be represented as:

.
or
./

To add a directory to the beginning of PATH:

export PATH=$HOME/bin:$PATH

This allows programs in `$HOME/bin` to be found before those in other directories.

---

## The SHELL Variable

The `SHELL` variable points to the user’s default command shell.

Example:

echo $SHELL

Output might show:

/bin/bash

---

## The PS1 Variable (Command Prompt)

`PS1` controls how the command prompt appears in the terminal.

Common prompt variables include:

\u  username  
\h  hostname  
\w  current working directory  
\!  command history number  
\d  current date  

These are usually defined inside single quotes.

Example:

PS1='\u@\h:\w$ '

---

## Saving and Restoring the Prompt

To temporarily save the current prompt:

OLD_PS1=$PS1

Then modify the prompt if desired.

To restore the original prompt:

PS1=$OLD_PS1
