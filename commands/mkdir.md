# mkdir command

## What it does
Creates new directories in the filesystem.

## Basic syntax
mkdir [options] directory_name

## Common options / examples
- mkdir dir1 dir2       # Create multiple directories
- mkdir -p a/b/c        # Create nested directories
- mkdir /tmp/example    # Create directory using absolute path

## Notes / mistakes
- mkdir fails if parent directories do not exist (unless -p is used)
