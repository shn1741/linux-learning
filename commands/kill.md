# kill

## Purpose
Sends a signal to a process, usually to terminate it.

---

## Common Usage

`kill <pid>`
- Sends the default SIGTERM signal

`kill -9 <pid>`
- Forcibly terminates process using SIGKILL

## Notes
- SIGKILL cannot be ignored by a process
- Use SIGKILL only if the process does not terminate normally.

