# Linux Documentation Tools

This file documents different ways to access Linux documentation.

---

## `man` Pages

The `man` command displays manual pages for Linux commands.

### Common Options

- `man command` – Open the manual for a specific command
- `man -f command` – Show a short description (equivalent to `whatis`)
- `man -k keyword` – Search manual page descriptions for a keyword (equivalent to `apropos`)
- `man -a command` – View all man pages for a command, one after another

### Navigation inside `man`

- Scroll up/down: Arrow keys or `PageUp` / `PageDown`
- Search: `/keyword` then Enter
- Quit: `q`

---

## GNU Info System (`info`)

The `info` tool provides a **hyperlinked, structured manual** for commands.

### Basic Usage

`info command`
- Opens the commands info page
- Displays a tree of nodes

### Navigation
- Move between nodes
 - `n`: next node
 - `p`: previous node
 - `u`: up one level
- Scroll inside a node: Arrow keys or `space`/`b`
- Quit: `q`

## Notes
- `info` pages often contain more detail than man pages
- Structured like a book with sections and sebsections


## Summary 
- Use `man` for quick reference and basic options
- Use `info` for structured, detailed documentation
- Both tools are essential for Linux mastery and troubleshooting
