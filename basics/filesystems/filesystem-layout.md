# Filesystem Layout


This section documents the standard Linux filesystem hierarchy and the purpose of important directories.

1. /bin and /sbin

`/bin` contains essential executable binaries.

Commands required to boot the system.

Commands required by all users (e.g. `ls`, `cp`, `mv`).

`/sbin` contains essential system administration binaries.

Typically used by the superuser (e.g. `fsck`, `ip`, `mount`).

On most modern distributions:

`/bin` → symlink to `/usr/bin`

`/sbin` → symlink to `/usr/sbin`


2. /proc

A pseudo-filesystem with no permanent data on disk.

Provides virtual files that expose kernel and system runtime information.

Examples of information available:

System memory usage

Mounted devices

Hardware and CPU details

Data is generated on demand and never stored permanently.


3. /dev

Contains device nodes (special files representing hardware devices).

Managed dynamically by the udev system.

Device nodes are created when devices are detected.

The directory is effectively empty on disk and populated at runtime.

Reflects the principle: everything in Linux is treated as a file.


4. /var

Contains variable data — files that change in size and content while the system runs.

Common subdirectories include:

`/var/log` – system and application log files

`/var/tmp` – temporary files preserved across reboots

`/var/spool` – queued data (e.g. print queues, mail)

`/var/lib` – application state, package, and database files

Network service directories may also appear here:

`/var/ftp`

`/var/www`


5. /etc

Contains system-wide configuration files.

No binary executables are stored here.

Configuration applies to the whole system.

User-specific configuration files are stored in each user’s `/home` directory.



6. /boot

Contains files required to boot the system.

For each installed kernel, four key files typically exist:

`vmlinuz` – compressed Linux kernel used at boot

`initramfs` (also historically called `initrd`) – initial RAM filesystem used during boot

`config` – kernel configuration file (mainly for debugging)

`System.map` – kernel symbol table (mainly for debugging)



7. /lib and /lib64

Contain shared libraries required by essential binaries in `/bin` and `/sbin`.

Libraries provide common code used by multiple applications.

On most modern systems:

`/lib` → symlink to `/usr/lib`

`/lib64` → symlink to `/usr/lib64`


8. /media, /run, and /mnt

Used for mounting filesystems and removable media.

`/run`:

Modern systems mount removable devices here dynamically.

Example:

`/run/media/username/usbdevice`

`/media`:

Historically used for removable devices.

`/mnt`:

Traditionally used for temporary or manual mounts.



9. Additional Directories Under /

`/opt` – optional or third-party application software

`/sys` – virtual filesystem exposing kernel and device information

`/srv` – data served by services (e.g. web, FTP)

`/tmp` – temporary files (often cleared on reboot)

`/usr` – user programs and data (detailed below)



10. /usr

Contains programs and data not essential for early system boot.

Major subdirectories include:

`/usr/bin` – user command binaries

`/usr/sbin` – system administration binaries

`/usr/lib`, `/usr/lib64` – shared libraries

`/usr/share` – architecture-independent data (docs, icons, man pages)

`/usr/src` – source code (e.g. kernel sources)

`/usr/include` – header files

`/usr/local` – locally installed software

