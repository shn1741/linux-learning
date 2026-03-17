## Recalling Previous Commands

The shell keeps a history of previously executed commands, which can be reused instead of typing them again.

### Viewing Command History

Use:

history

The history is stored in:

~/.bash_history

You can also navigate through previous commands using:

- Up arrow → previous command  
- Down arrow → next command  

---

### History Environment Variables

Some variables control how command history is stored:

- HISTFILE → location of the history file  
- HISTFILESIZE → maximum number of lines in the history file  
- HISTSIZE → number of commands stored in memory  
- HISTCONTROL → controls how commands are stored  
- HISTIGNORE → specifies commands that should not be saved  

---

### Reusing Previous Commands

Execute the previous command:

!!

Search previous commands:

CTRL + R

Other useful shortcuts:

!$ → last argument of previous command  
!n → execute command number n  
!string → execute most recent command starting with "string"  

---

### Keyboard Shortcuts

Some useful shortcuts in the shell:

CTRL + L → clear screen  
CTRL + D → exit shell  
CTRL + A → move to beginning of line  
CTRL + E → move to end of line  
CTRL + W → delete previous word  
CTRL + U → delete from beginning to cursor  
Tab → auto-complete files, directories, and commands  

---
