# Lab: Managing Users and Groups

## Objective

Practice creating users and groups, modifying group membership, and observing how these changes are reflected in system files such as `/etc/passwd` and `/etc/group`.

---

## Part 1: Create a Test Group

Create a new group:

sudo groupadd labgroup

Verify the group exists:

cat /etc/group | grep labgroup

Output:

labgroup:x:1001:

Observation:

A new entry appears in `/etc/group` showing the group name and its GID.

---

## Part 2: Create a Test User

Create a new user:

sudo useradd labuser

Check the user information:

id labuser

Output: 

uid=1001(labuser) gid=1002(labuser) groups=1002(labuser)

Inspect the passwd file:

cat /etc/passwd | grep labuser

Output:

labuser:x:1001:1002::/home/labuser:/bin/sh

Observation:

A new line appears in `/etc/passwd` showing the username, UID, GID, home directory, and shell.

---

## Part 3: Add the User to the Group

Add the user to the new group:

sudo usermod -a -G labgroup labuser

Verify group membership:

groups labuser

Output:

labuser : labuser labgroup

Observation:

The output should show that `labuser` belongs to both its primary group and `labgroup`.

---

## Part 4: Inspect Group File After Modification

Check `/etc/group` again:

cat /etc/group | grep labgroup

Output:

labgroup:x:1001:labuser

Observation:

The user `labuser` now appears in the group entry.


---

## Part 5: Inspect User Information

Run:

id labuser

Output:

uid=1001(labuser) gid=1002(labuser) groups=1002(labuser),1001(labgroup)

Observation:

The information shows that user labuser is now part of a secondary group labgroup other than the primary group labuser. 

The output displays:

- UID
- primary GID
- all secondary groups

---

## Part 6: Inspect Skeleton Directory

List the skeleton directory:

ls /etc/skel

Observation:

Files in this directory are copied into a user's home directory when a new account is created.

---

## Part 7: Create a Persistent Alias

Open `.bashrc`:

nano ~/.bashrc

Add the following line:

alias linux-learning='cd ~/projects/linux-learning' 

Reload the configuration:

source ~/.bashrc

Test the alias:

linux-learning

Observation:

The alias now works and will persist in future shell sessions.

---

## Part 8: Cleanup

Remove the test user and its home directory:

sudo userdel -r labuser

Remove the test group:

sudo groupdel labgroup

Verify removal:

cat /etc/passwd | grep labuser
cat /etc/group | grep labgroup

Observation:

Both the user and group entries should be removed from the system files.

---

## Reflection

This lab demonstrated how Linux manages user and group information using system files. Creating users and groups updates `/etc/passwd` and `/etc/group`, and group membership controls shared permissions between users.

### What I understood from this lab

- Users are uniquely identified by a UID.
- Groups organize users and control shared permissions.
- `/etc/passwd` stores user account information.
- `/etc/group` stores group membership information.
- Tools like `useradd`, `groupadd`, and `usermod` modify these system records.
