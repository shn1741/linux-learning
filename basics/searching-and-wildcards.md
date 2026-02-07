# Searching and Wildcards in Linux

This file documents common tools used to locate files and match patterns.

---

## `find`

Searches for files and directories in real time.

`find /path -name filename`
Common options: 
 - -name: Case sensitive name match
 - -iname: Case insensitive name match
 - -type: File type (directory, symbolic link, file)

### Examples

`find . -name "*.txt"`
`find / -type d`
`find . -iname "readme.md"`


## Locate

`locate filename`
 - Much faster than find
 - Database may be outdated
 - Updated using `updatedb`


## Wildcards

(*)
- Matches zero or more characters
`ls *.txt`

(?) 
- Matches exactly one character
`ls file?.txt`

[set]
- Matches any one character from the set
`ls file123.txt`

[!set]
- Matches any character not in the set
`ls file[!0-9].txt

### Notes
 - Wildcards are expanded by the shell, not the command
 - `Find` is more powerfull but slower than `locate`
