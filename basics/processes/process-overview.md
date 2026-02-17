# Process Overview

## What Is a Process
A process is one or more related tasks executing instructions on the CPU.  
Processes use system resources such as CPU time, memory, files, and I/O devices.

---

## Types of Processes

### Interactive Processes
Processes started by users that require interaction, such as commands run in a terminal.

### Batch Processes
Processes that run without user interaction, often scheduled to run automatically.

### Daemons
Background processes that provide system services and usually start at boot time.

### Threads
Lightweight units of execution within a process. A single process may contain multiple threads.

### Kernel Threads
Threads that run in kernel space and perform system-level tasks. Users neither start nor terminate them and have little control over them.

---

## Process Scheduling and States
The Linux kernel uses a function called the **scheduler** to switch processes on and off the CPU.

- When a process is ready to run, it is placed on a **run queue**
- A running process may:
  - Execute instructions
  - Wait for CPU time
  - Enter a **sleep state** while waiting for resources
- Processes can transition between multiple states during their lifetime
