# Command-Line Concepts: Paths and Terminals

## Absolute vs Relative Paths
- Absolute paths start from root `/` (example: /etc/passwd)
- Relative paths start from the current directory (example: ../folder)
- Useful with `cd` to navigate filesystems

## Virtual Terminals
- Linux has multiple virtual terminals (VTs)
- Switch using Ctrl + Alt + F1..F6 (varies by distro)
- Allows multiple independent sessions

## GUI Start/Stop Commands
- Stop GUI: `sudo systemctl stop gdm` or `sudo telinit 3`
- Start GUI: `sudo systemctl start gdm` or `sudo telinit 5`
- Useful for troubleshooting or working in a terminal-only session

## Notes / mistakes
- Make sure to save your work before stopping GUI
- Still don't understand the Relative path
