# Process Attributes

## Process and Thread IDs

### PID (Process ID)
Each process is assigned a unique Process ID (PID).  
The system uses the PID to track process state, resource usage, and ownership.

- PIDs are assigned in ascending order as processes are created

### PPID (Parent Process ID)
The PID of the process that created the current process.

### TID (Thread ID)
Identifies individual threads within a process.

- In single-threaded processes, the PID and TID are the same

---

## User and Group IDs

### RUID (Real User ID)
Identifies the user who started the process.

### EUID (Effective User ID)
Determines the permissions the process currently has.

### RGID (Real Group ID)
Identifies the primary group of the user who started the process.

### EGID (Effective Group ID)
Determines group-based permissions during execution.

---

## Process Priorities

### Niceness
Processes have a priority value called **nice value** (or niceness).

- Lower nice value → higher priority
- Higher nice value → lower priority

### Changing Priority
The `renice` command is used to change the priority of a running process.
