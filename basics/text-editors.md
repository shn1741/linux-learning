# Text Editors in Linux

## Overview

Linux provides several text editors that can be used to create and modify files. These include simple terminal editors, graphical editors, and more advanced editors with powerful capabilities.

Editors covered in this chapter:

- nano
- gedit
- vi (vim)
- emacs

---

## Creating Files Without an Editor

Files can be created directly from the command line without opening a text editor.

### Using echo

Text can be written to a file using output redirection.

Example:

echo line one > filename
echo line two >> filename
echo line three >> filename

Notes:

- `>` writes to a file and **overwrites existing content**.
- `>>` **appends** text to an existing file.

---

### Using cat with redirection

Multiple lines can be written to a file using a here-document.

Example:

cat << EOF > filename
line one
line two
line three
EOF

This allows writing multiple lines before saving them to the file.

---

## Nano and Gedit

### nano

`nano` is a simple terminal-based text editor.

To create or edit a file:

nano filename

Characteristics:

- Easy to learn
- Commonly available on Linux systems
- Help and command shortcuts are displayed at the bottom of the screen

---

### gedit

`gedit` is a graphical text editor that is part of the GNOME desktop environment.

Characteristics:

- Graphical interface
- Simple and easy to use
- Suitable for desktop environments

---

## vi and emacs

`vi` and `emacs` are advanced editors with powerful features. They have both terminal and graphical versions.

They are more difficult to learn initially but very efficient once mastered.

---

## Modes in vi

`vi` operates using different modes.

### Command Mode

Default mode when a file is opened.

- Keystrokes are interpreted as commands.
- Used for navigation and editing operations.

### Insert Mode

Used for typing text into the file.

Enter insert mode:

i

Exit insert mode:

Esc

---

### Line Mode

Enter line mode by typing:

:

This mode is used for commands such as saving, quitting, or running certain operations.

Return to command mode by pressing:

Esc

---

## Working With Files in vi

Open a file:

vim filename

Recover a crashed editing session:

vim -r filename

Read another file into the current file:

:r filename

Write file to disk:

:w

Write to a new file:

:w filename

Force overwrite:

:w! filename

Save and exit:

:x  
:wq

Quit:

:q

Quit without saving:

:q!

---

## Cursor Movement in vi

Basic movement keys:

h  move left  
l  move right  
j  move down  
k  move up  

Other useful movements:

0  move to beginning of line  
$  move to end of line  
w  move to beginning of next word  

File navigation:

:0  move to beginning of file  
:$  move to last line of file  

Page movement:

CTRL-F  move forward one page  
CTRL-B  move backward one page

---

## Searching in vi

Search for text using:

/search_text

Navigation:

n  move to next match  
N  move to previous match

---

## Working With Text in vi

Insert and append:

a  append text after cursor  
A  append text at end of line  
i  insert text before cursor  
I  insert text at beginning of line  

Creating new lines:

o  open new line below  
O  open new line above  

Replacing text:

r  replace single character  
R  replace text continuously

Deleting text:

x  delete character  
Nx  delete N characters  

dw  delete word  
D   delete rest of line  

dd   delete current line  
Ndd  delete N lines

Undo:

u  undo last operation

Copy and paste:

yy   copy (yank) current line  
Nyy  copy N lines  

p    paste copied text

---

## Using External Commands in vi

Open a shell temporarily:

:sh

When the shell exits, the editor resumes.

Execute a command from within vi:

:!command
