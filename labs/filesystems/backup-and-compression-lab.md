# Lab: Backup and Compression Practice

## Objective

Practice:
- Backing up directories using rsync
- Understanding dry-run behavior
- Using --delete safely
- Creating compressed archives
- Comparing compression sizes
- Creating a disk image safely using dd

---

## Part 1: Setup Test Environment

### Create working directories

Command:

mkdir -p ~/backup-lab/source
mkdir -p ~/backup-lab/destination

### Create sample files

Command:

echo "Linux foundation learning" > ~/backup-lab/source/file1.txt
echo "Switching careers into IT" > ~/backup-lab/source/file2.txt

### Verify files

Command:

ls -l ~/backup-lab/source

Output:

- file1.txt (26 bytes)
- file2.txt (26 bytes)

Observation:

Two text files were created in the source directory. Each file is 26 bytes because echo adds a newline character at the end.

## Part 2: Testing rsync
`rsync -av --dry-run ~/backup-lab/source/ ~/backup-lab/destination/`
Output:
sending incremental file list
./
file1.txt
file2.txt

sent 110 bytes  received 25 bytes  270.00 bytes/sec
total size is 52  speedup is 0.39 (DRY RUN)

Explanation: This showed that file1.txt and file2.txt would be copied from source to destination
because destiation was empty

`rsync -av ~/backup-lab/source/ ~/backup-lab/destination/`
Output:
sending incremental file list
./
file1.txt
file2.txt

sent 242 bytes  received 57 bytes  598.00 bytes/sec
total size is 52  speedup is 0.17

Explanation: This actually copied the files.

Running again: `rsync -av ~/backup-lab/source/ ~/backup-lab/destination/`
Output: 
sending incremental file list

sent 97 bytes  received 12 bytes  218.00 bytes/sec
total size is 52  speedup is 0.48

Explanation: No files were listed because destination already matched source.

## Part 3: Testing --delete
1. File deletion: `rm ~/backup-lab/source/file2.txt`

2. Delete run: 
Output: 
sending incremental file list
deleting file2.txt
./

sent 83 bytes  received 28 bytes  222.00 bytes/sec
total size is 26  speedup is 0.23
 
`ls -l ~/backup-lab/destination`

Explanation: file2.txt was removed from destination

## Part 4: Compression Comparison
Command used to create Big File
`yes "linuxcareer" | head -n 10000 > ~/backup-lab/source/bigfile.txt`
Checking file size: `ls -lh ~/backup-lab/source`
bigfile.txt size: 118K
Creating compressed archives:
`tar -czvf backup.tar.gz source/`
`tar -cjvf backup.tar.bz2 source/`
`tar -cJvf backup.tar.xz source/`
Comparing sizes: 
`ls -lh backup.*`
backup.tar.gz   554K
backup.tar.bz2  307K
backup.tar.xz   360K

Explanation: bzip2 produced the smallest archive in this case. Compression efficiency depends on the data pattern.

## Part 5: Archiving with tar
Create non compressed archive:
`tar -cvf archive.tar source/`
Then:
`ls -lh archive.tar`
This proves that `tar` alone does not compress. It just groups files.

Extract Archive:
Create restore folder:
`mkdir restore-test`
`tar -xvf archive.tar -C restore-test/`

Verify:
`ls restore-test`

All files were successfully extracted.

## Part 6: Safe dd Practice
`dd if=/dev/zero of=disk.img bs=1M count=50 status=progress`
Proof: `ls -lh disk.img`
Output:
-rw-rw-r-- 1 shan shan 50M فروری  25 14:44 disk.img

Explanation: Created 50MB disk image file (not a real disk), to understand how dd copies raw data.
---

## Reflection
- rsync is incremental, second run copies nothing if unchanged

- --delete can remove files in destination to match source

- tar groups files; gzip/bzip2/xz compress differently

- Repetitive data compresses a lot

- dd copies raw data and must be used carefully

What I understood from this lab:
- rsync only transfers differences, unlike cp. 
- The `--delete` option must be used carefully as it can unintentionally delete unwanted files from the destination. 
- Compression efficiency depends on the data pattern, repetitive data compresses dramatically and this is why in my lab the results for compression size were counter intuitive. 
- `tar` archives and then compresses.
- `dd` copies raw data blocks. It is extremely dangerous. 
