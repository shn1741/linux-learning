# Accounts, Users and Groups

## Overview

Linux is a multi-user system. Each user has a unique identifier and belongs to one or more groups. Users and groups help control permissions, access, and system organization.

This section covers:

- Identifying users
- Shell startup files
- Creating aliases
- Understanding users and groups
- Managing users and groups
- Root privileges and administrative access

---

## Identifying the Current User

The following commands help identify users currently logged into the system.

List users currently logged in:

who

Show the current user:

whoami

Show detailed login information:

who -a

---

## User Startup Files

The shell reads configuration files when starting a session. These files configure the user's environment.

Global configuration files are located in:

/etc

These affect all users.

User-specific configuration files are located in each user’s home directory and can override global settings.

These startup files can configure things such as:

- command aliases
- prompt customization
- environment variables
- executable search paths

---

## Order of Startup Files

When a **login shell** starts, the system reads:

/etc/profile

Then the shell searches for the following files in order:

~/.bash_profile  
~/.bash_login  
~/.profile  

The first file found is executed and the others are ignored.

When opening a **new terminal window**, it is not considered a login shell. Instead the following file is executed:

~/.bashrc

---

## Creating Aliases

Aliases allow users to create shortcuts for long or frequently used commands.

Example:

alias linux-learning='cd /home/shan/projects/linux-learning'

Typing `linux-learning` will now change the directory to that path.

To make aliases persistent across sessions, they are usually added to:

~/.bashrc

---

## Basics of Users and Groups

Each user has a **User ID (UID)**.

User information is stored in:

/etc/passwd

Users belong to groups which determine shared permissions.

Groups also have identifiers called **Group IDs (GID)**.

Group information is stored in:

/etc/group

Typical UID values:

- System users: below 1000
- Normal users: 1000 and above

By default, a user belongs to a **primary group** that usually has the same GID as the user's UID.

---

## Structure of /etc/passwd

Example entry:

john:x:1001:1001:John Garfield:/home/John:/bin/bash

Field meanings:

- john → username
- x → password placeholder
- 1001 → user ID (UID)
- 1001 → group ID (GID)
- John Garfield → comment field (full name)
- /home/John → home directory
- /bin/bash → default shell

---

## Adding and Removing Users

Add a new user:

sudo useradd user

This creates:

- a user entry in `/etc/passwd`
- a home directory `/home/user`
- default files copied from `/etc/skel`

Example entry created in `/etc/passwd`:

user:x:1001:1001::/home/user:/bin/bash

Remove a user:

sudo userdel user

This removes the account but keeps the home directory.

Remove the user and home directory:

sudo userdel -r user

View user information:

id

View information for a specific user:

id username

Example output:

uid=1002(bjmoose) gid=1002(bjmoose) groups=106(fuse),1002(bjmoose)

---

## Adding and Removing Groups

Create a new group:

sudo /usr/sbin/groupadd anewgroup

Delete a group:

sudo /usr/sbin/groupdel anewgroup

Add a user to a group:

sudo /usr/sbin/usermod -a -G anewgroup user

Check which groups a user belongs to:

groups user

Modify group properties:

groupmod -g newgid groupname  
groupmod -n newname groupname

Group utilities update the `/etc/group` file.

---

## Removing a User from a Group

To remove a user from a group, specify the groups the user should remain in:

sudo /usr/sbin/usermod -G group1,group2 user

Deleting a group will also remove users from that group.

---

## The Root Account

The **root account** is the superuser account with full system privileges.

Because root can modify or delete any file, it must be used carefully.

---

## su and sudo

`su` allows switching users, commonly to the root account.

Example:

su

However, using `su` frequently can be risky because it grants full root access.

`sudo` is generally safer. It allows users to execute a single command with elevated privileges.

Example:

sudo command

Many Linux distributions enable `sudo` for the main user account by default.

To check if a user belongs to the sudo group:

groups user

Configuration files for sudo are located in:

/etc/sudoers  
/etc/sudoers.d/
