## File Permissions

Linux controls access to files using permissions and ownership.

---

### File Ownership

Each file has:

- an owner (user)
- a group

Commands:

chown → change file owner  
chgrp → change group ownership  

---

### File Permissions

Each file has three types of permissions:

- read (r)
- write (w)
- execute (x)

These permissions apply to three categories:

- user (owner)
- group
- others  

Example format:

rwx:rwx:rwx

---

### Changing Permissions with chmod (Symbolic Mode)

Example:

chmod uo+x,g-w file

This means:

- add execute permission to user and others  
- remove write permission from group  

---

### Numeric (Octal) Permission System

Permissions can also be represented using numbers:

- 4 → read  
- 2 → write  
- 1 → execute  

Add them together:

- 7 → read + write + execute  
- 6 → read + write  
- 5 → read + execute  

Example:

chmod 765 file

This means:

- owner → rwx (7)  
- group → rw (6)  
- others → r-x (5)  
