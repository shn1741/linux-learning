# ps

## Purpose
Displays information about currently running processes.

---

## Common Usage

`ps`
- Shows processes associated with the current terminal

`ps aux`
- Displays all processes for all users with the detailed information. 

---

## System V Style Options

`ps -ef`
- Displays all processes on the system in full format.

`ps -elf`
- Displays one line of information for every thread.

`ps -u username`
- Displays processes owned by a specific user.

`ps -f` 
- Displays full format including parent process ID (PPID).

`ps -l`
- Adds columns for priority (PR) and niceness (NI).

## BSD Style Options

`ps aux`
- Displays all processes for all users.

`ps axo, pid, user, cmd`
- Allows selecting specific attributes to display.

