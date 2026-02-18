# top

## Purpose
Displays real-time information about running processes and system resource usage.

---

## Usage

`top`

## Key Information Displayed
- CPU usage
- Memory usage
- Load averages
- List of active processes

## Common interactive commands
- `q`-- Quit
- `k`-- Kill a process
- `r`-- Change priority (renice)

---

## Understanding top Output

### First Line
- System uptime
- Number of users logged in
- Load averages

---

### Second Line
Displays the total number of processes and how many are:
- Running
- Sleeping
- Stopped
- Zombie

---

### Third Line (CPU Usage)
- us: user processes
- sy: kernel processes
- ni: low-priority user processes
- id: idle time
- wa: waiting for I/O
- hi: hardware interrupts
- si: software interrupts
- st: stolen time

---

### Fourth and Fifth Lines
Displays physical memory and swap usage:
- Total
- Used
- Free

---

### Process List Columns
- PID
- USER
- PR / NI
- VIRT, RES, SHR
- S (status)
- %CPU
- %MEM
- TIME+
- COMMAND

