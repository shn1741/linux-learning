# Network File System (NFS)

## Overview
NFS allows filesystems to be shared across physical systems over a network.

---

## NFS on the Server

Start NFS services:
`sudo systemctl start nfs`

The /etc/exports file defines which directories are shared and theri permissions.

Example:

/projects *.example.com(rw)

After modifying exports: 

`exportfs -av`

Restart NFS:

`sudo systemctl restart nfs`

Enable at boot:

`sudo systemctl enable nfs`

---

## NFS on the Client
To mount automatically at boot, add an entry to `/etc/fstab`:

`servername:/projects /mnt/nfs/projects nfs defaults 0 0`

For a one-time mount:

`sudo mount servername:/projects /mnt/nfs/projects`

Use the `nofail` option if the server may be unavailable at boot

