# Backing Up and Compressing Data

## Overview

This chapter covered methods for backing up data, compressing files, and copying disk data in Linux. The main tools discussed were `cp`, `rsync`, compression utilities (gzip, bzip2, xz, zip), `tar`, and `dd`.

---

## 1. Backing Up Data

### Using cp

The `cp` command is used to copy files and directories.

Example:

cp -r project-X project-X-backup

Notes:

- Works locally.
- Can copy across systems only if using mounted filesystems (like NFS).
- Copies everything again (not incremental).

---

### Using rsync

`rsync` is more efficient than `cp` because it copies only changed files instead of everything.

It can also work across machines over SSH.

Example:

rsync -r project-X archive-machine:archives/project-X

This syncs the local project-X directory to the directory on archive-machine.

Important:

`rsync` can be destructive, especially when using `--delete`. It is recommended to test first:

rsync --dry-run sourcedir destdir

Common useful combination:

rsync --progress -avrxH --delete sourcedir destdir

Option explanation:

-a  archive mode  
-v  verbose  
-r  recursive  
-x  stay on one filesystem  
-H  preserve hard links  
--delete  remove files in destination not present in source  
--progress  show transfer progress  

---

## 2. Compressing Data

Compression reduces file size to save space or speed up transfer.

Tools covered:

- gzip (fast, moderate compression)
- bzip2 (slower, better compression)
- xz (slowest, best compression)
- zip (cross-platform)

Smaller archives generally take longer to create.

---

## 3. Archiving and Compressing with tar

`tar` groups multiple files into a single archive.

Create archive:

tar -cvf archive.tar folder/

Extract archive:

tar -xvf archive.tar

Create compressed archive:

tar -czvf archive.tar.gz folder/      (gzip)
tar -cjvf archive.tar.bz2 folder/     (bzip2)
tar -cJvf archive.tar.xz folder/      (xz)

---

## 4. Disk to Disk Copying with dd

The `dd` command copies raw disk data.

Example:

dd if=/dev/sda of=/dev/sdb bs=4M status=progress

if = input file  
of = output file  
bs = block size  

Warning: `dd` can overwrite entire disks and must be used carefully.

---

## 5. Lab Practice

(Completed separately below.)
