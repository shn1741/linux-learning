# Process Metrics and Control

## Load Averages

Load average represents the average number of processes that are either:
- Running on the CPU, or
- Waiting to be run

Load averages can be viewed using:
- `w`
- `top`
- `uptime`

A load average of **1.00 per CPU** means the CPU is fully utilized but not overloaded.
- Below 1.00 → system has spare capacity
- Above 1.00 → system is overloaded
- Very high values may indicate a runaway process

---

## Foreground and Background Processes

By default, all processes run in the foreground.

### Foreground process behavior
- Uses the terminal
- Blocks input until it finishes

### Background process behavior
- Runs without occupying the terminal
- Started by appending `&` to the command

`command &`

### Suspending and Terminating Processes
- Ctrl + Z: suspends a foreground process. 
- Ctrl + C: terminates a foreground process. 
A suspended process can be resumed later. 

### Job Control

Running Jobs in Background or Foreground
- `bg` resumes a suspended job in the background
- `fg` brings a background job to the foreground

---

## Job Control

The `jobs` command lists job started from the current terminal session.
`jobs`
`jobs -l`
- Background jobs are tied to the terminal session
- If you log out, jobs started from that terminal are no longer tracked

