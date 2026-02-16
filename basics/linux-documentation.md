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

---

## Built-in Help and `--help`

### `help` (Built-in Commands)

The `help` command provides documentation for **shell built-in commands**.

`help cd`
`help exit`
- Works only for shell built-ins
- Faster than using `man` for built-in commands
- Output is concise and command-focused

### --help

`command --help`
This displays:
- Usage syntax
- Common options
- Short explanations

Notes: 
- Quickest way to see available flags
- Output is brief compared to man pages
- Not standardized across all commands


## Other documentation sources

### Desktop Help Systems

Linux desktop environments often include graphical help systems.
ExampleL:
- GNOME desktop help (gnome-help)

Characteristics:
- User friendly
- Intregrated with the desktop environment
- Useful for GUI-based tools and settings

### Package Documentation

Installed packages often include documentation files.

Common locations:
- /usr/share/doc/
- /usr/share/doc/package-name/

These may include:
- README files
- Configuration examples
- Changelogs

### Online Documentation

External documentation sources include:
- Official project documentation
- Communnity wikis
- Forums and Q&A sites

Examples:
- Distribution documentation (Ubuntu, Debian, Arch)
- Man pages repositories
- Developer guides

Online resources are useful when:
- Local documentation is insufficient 
- Learning advanced or niche topics
- Troubleshooting uncommon issues

## Final Notes
- `man` and `info` are the primary local documentation tools
- `help` is best for shell built-ins
- `--help` provides quick command usage
- External documentation complements local resources
