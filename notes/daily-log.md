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
