# Partitions and Mounting

## Linux Partitions
Partitions organize disk contents according to data type and usage.

Common partitions include:
- `/` (root): contains essential system files
- `/home`: stores files owned by regular users

---

## Mount Points
To use a filesystem, it must be mounted at a **mount point**, which is a directory.

- The directory may be empty or non-empty
- It must exist before mounting

---

## Mounting and Unmounting Filesystems

Mounting example:
`sudo mount /dev/sda5 /home`

Unmounting example:
`sudo umount /home`

Persistent Mounting:
- To mount filesystems automatically at boot time, entries are added to /etc/fstab.

---

## Viewing Mounted Filesystems

`mount`

`df -Th`
- Displays filesystem type, usage, and available space.

