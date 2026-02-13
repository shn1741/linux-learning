# Linux Package Management

This file documents how software is installed, updated, and managed on Linux
systems using package managers.

---

## Package Management Overview

Linux uses package management systems to:
- Install software
- Update software
- Remove software
- Handle dependencies automatically

Package managers ensure system consistency and security.

---

## High-Level vs Low-Level Package Tools

### Low-Level Package Tools
Low-level tools work directly with package files but do **not** resolve
dependencies automatically.

Examples:
- `dpkg` (Debian-based systems)
- `rpm` (Red Hat-based systems)

Characteristics:
- Install or remove individual package files
- Dependency resolution must be handled manually
- Rarely used directly by users

---

### High-Level Package Tools
High-level tools manage dependencies and repositories automatically.

Examples:
- `apt` (Debian/Ubuntu)
- `dnf` / `yum` (RHEL-based)
- `zypper` (SUSE)

These are the tools used for everyday system management.

---

## Common `apt` Commands (Debian/Ubuntu)

### Update Package Index
`sudo apt update`
- Refreshes list of available packages

`sudo apt upgrade`
- Upgrades installed packages to newer versions

`sudo apt install package_name`

`sudo apt remove package_name`

`sudo apt autoremove`
- Remove unused dependencies

`apt-cache search package_name`
- Show packages named package_name

`apt-cache dumpavail`
- Show all available packages

`dpkg --search file`
- What package is file part of

`dpkg --list`
- Show all installed packages

`dpkg --listfiles package_name`
- Get information on package

