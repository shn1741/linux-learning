# Shell I/O, Redirection, and Pipes

This file documents how Linux handles input and output streams
and how commands can be connected together.

---

## Standard File Streams

Linux processes use three standard data streams:

- **stdin (0)** – Standard input (keyboard by default)
- **stdout (1)** – Standard output (terminal by default)
- **stderr (2)** – Standard error output (terminal by default)

These streams allow commands to communicate with the user or other commands.

---

## I/O Redirection

Redirection allows changing where input comes from or where output goes.

### Output Redirection

`command > file`
- Redirects standard output to a file

### Input Redirection

`command < file`
- Uses file as stdin

### Error Redirection

`command 2> error.txt`
- Redirects stderr to a file

`command &> all.txt`
- Redirects stdout and stderr together


## Pipes
A pipe (|) sends the stdout of one command as the stdin of another

`command1 | command2`

Pipe allows commands to be combined into powerfull workflows

