# Comparing Files and File Types

## 1. Comparing files and directories with `diff`

- `diff` shows differences between two text files.
- Common options:
  - `-c` : context output
  - `-r` : recursive, compare directories
  - `-i` : ignore case
  - `-w` : ignore all whitespace
  - `-q` : brief summary of differences
- Usage:
`diff filename1 filename2`
For binary files use `cmp` instead. 

## 2. Using `diff3` and `patch`

- `diff3` compares three files using one as the reference:
`diff3 Myfile Commonfile Yourfile`

- Creating a patch from differeces:
`diff -Nur originalfile newfile > patchfile`

- Applying a patch to a single file: 
`patch originalfile < patchfile`

- Applying a patch to a directory tree:
`patch -p1 < patchfile`

- Test patch without making changes: 
`patch --dry-run originalfile < patchfile`

## 3. Using the `file` utility

- Determines the real type of a file (text, binary, executable, etc.)
- Usage:
`file filename`
 - Useful to verify unknown files or confirm file format before operation. 

