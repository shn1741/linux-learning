## 2026-01-22

### Commands Learned
- cd, ls, pwd
- Practiced navigating directories using the terminal

### Concepts Learned
- Virtual terminals and how to access them
- Absolute vs relative paths
- Stopping/starting GUI with systemctl or telinit

### Networking
- Watched a lesson on OSI model layers
- Learned basic attributes of each layer
- Still unclear on the details and what each layer entails

### Notes / reflections
- Need to watch the video on OSI model layers again. 
- Need to understand the path for relative paths. 
- Progress feels good; first batch of commands documented and pushed

---

## 2026-01-23

### Linux (continued)
- Documented file deletion commands:
  - rm
  - rm -r
  - rm -f
  - rm -i
- Documented filesystem commands:
  - mkdir, rmdir, touch, tree

- Reinforced understanding of safe vs unsafe deletion practices
- Continued organizing command documentation into logical batches

### Networking (review + refinement)
- Revisited the OSI model to strengthen conceptual understanding
- Focused on:
  - Purpose of each layer
  - What kind of data and responsibilities belong to each layer
- Clarified gaps from the initial lesson

### Cloud Computing (introduction)
- Watched introductory cloud lesson
- Understood client-server model using a coffee shop analogy
- Learned key cloud concept:
  - Pay only for what you use (AWS)
  - Compared cloud services vs on-premises data centers

- Couldn't update the daily log yesterday


## Log Gap Note

There was a gap in daily logging during which learning continued. Key topics
from this period have been documented in the repository under their
respective sections.

---

## 2026-02-16

### Linux
- Documented Linux documentation tools:
  - man pages and common options
  - GNU Info system
  - help and --help usage
  - Other documentation sources

### Networking
- Could'nt continue networking course due to an expired coursera subscrition.
  Will continue as soon as I subscribe again.

### Notes
- Focused on consolidating documentation rather than new topics.

---

## 2026-02-18

- Studied process metrics and job control
- Learned load averages and process states
- Documented ps, top, pstree, and job control commands

---

## 2026-02-20

- Studied scheduling processes using at, cron, anacron, and sleep
- Completed lab exercises for at and cron
- Studied Linux filesystems, partitions, mounting, and NFS
- Documented filesystem types and network filesystem concepts

---

## 2026-02-23

### Concepts
- Studied filesystem layout. 
- Learned to compare files and directories using `diff` and `cmp`.
- Practiced `diff3` to compare three files with one as reference.
- Learned to create and apply patches with `diff` + `patch`.
- Learned to apply patches to directories using `patch -p1`.
- Explored `file` utility to determine real file types (text, binary, executable).

### Notes
- Practice needed for scheduling jobs, wildcards.
- Chapter 9 and 10 will require more revision. Very important chapter.
- Cloud concepts put on hold for the moment. Will reflect that in the repo structure at some time. 
- Networking fundamentals course back online. Will need to give more time to catch up. 

---

## 2026-02-25

### Summary
Studied backing up and compressing data in Linux. Covered rsync, tar, different compression methods
(gzip, bzip2, xz), and basic usage of dd for disk imaging.

### Lab Work
Practiced syncing directories with rsync, tested --delete, compared compression sizes using different
algorithms, and created a sample disk image safely with dd.

### What Challenged Me
Archiving is straight forward. How ever compressing gets a bit confusing, especially since todays lab
produced counter intuitive results. xz was supposed to give the smallest file size followed by bzip2
and then gzip, however, since the archive file was very repetitive it affected the compression. 

### Overall Reflection
The backup and compression lab helped me retain and understand concepts and commands much better. I'm 
much more confident in using them now.

---

## 2026-03-06

### Summary

Studied Linux text editors including nano, gedit, vi, and emacs. Learned how files can be created directly from the terminal using `echo` and `cat` with redirection, and explored the basic structure and modes of the `vi` editor.

### Lab Work

Reviewed and practiced basic file creation from the terminal and went through common navigation and editing commands used in `vi`. Also used `vimtutor` and went through the whole tutorial. 

### What Challenged Me

Keeping track of when commands operate in command mode versus insert mode. Theres a lot of keys for a lot of different things. Its only going to get easier with practice. Navigating within the lines may be the hardest thing for me. 

### Overall Reflection

This chapter introduced several editors used in Linux environments. Nano appears straightforward, while `vi` seems much more powerful but will require more practice to become comfortable with.

---

# 2026-03-12

Documented backing up and compressing data which I had studied much earlier. Its lab was documented on the same day. 

---

## 2026-03-14

### Summary

Started Chapter 12 on the user environment. Today’s section focused on accounts, users and groups. Learned how to identify the current user, how shell startup files configure the environment, and how aliases can be used to simplify commands. Also learned where Linux stores information about users and groups and how UID and GID work.

### Lab Work

Ran a small lab where I created a test user and a group, added the user to the group, and then checked how the changes appeared in `/etc/passwd` and `/etc/group`. Also practiced creating a persistent alias using `.bashrc`.

### What Challenged Me

While cleaning up the lab I tried deleting the test user and got a “user not found” type message even though I thought I had created it earlier. Had to double-check what actually existed on the system.

### Overall Reflection

This part of the chapter made the user and group system feel more concrete. Seeing how commands like `useradd`, `usermod`, and `groupadd` actually modify system files helped me understand how Linux manages accounts behind the scenes.

---

## 2026-03-17

### Summary

Continued Chapter 12 on the user environment and studied environment variables. Learned what environment variables are, how they influence the behavior of the shell and other programs, and how to view them using commands like `env`, `set`, and `export`.

### Lab Work

Ran a small lab where I viewed existing variables, created a new variable, exported it, modified the `PATH` variable, and experimented with the `PS1` variable to temporarily change the command prompt.

### What Challenged Me

Understanding the difference between variables that exist only in the current shell and variables that are exported so child processes can use them.

### Overall Reflection

Working with environment variables made it clearer how the shell environment is configured. Seeing how variables like `HOME`, `PATH`, and `PS1` directly affect the terminal helped connect the concepts to actual behavior in the shell.

---

## 2026-03-17

### Summary

Finished Chapter 12 by studying command history and file permissions. Learned how to recall previous commands using history and shortcuts, and how Linux tracks and stores command history. Also studied file permissions and ownership, including how to use chmod, chown, and chgrp, and how permission values work both symbolically and numerically.

### Lab Work

Practiced recalling commands using history, !!, and CTRL+R, and tried different keyboard shortcuts. Also experimented with file permissions by changing them using both symbolic and numeric modes with chmod.

### What Challenged Me

Remembering the different ways of recalling commands and understanding the numeric permission system at first.

### Overall Reflection

This part of the chapter felt more practical and directly useful. File permissions especially seem very important and something I’ll need to practice more to get comfortable with.
