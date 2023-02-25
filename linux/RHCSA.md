# RHCSA

# Understand and use essential tools for handling files, directories, command-line environments, and documentation

## Users

Commands 

```bash
# see data about user
id USER

grep -i USER /etc/passwd

# view who is logged
who

# view last logins
last

# switch supersuer and user
su -
su USER
```

### /etc/passwd

The passwd file contains data about the users in this format:

`name:password:UID:GID:GECOS:directory:shell`

The password is storaged encrypted in the `/etc/shadow`file.

Service accounts have an UID < 1000.

### /etc/group

The group file stores the data about groups in this format:

`name:password:GID:user list`

### /etc/sudoers

The sudoers file defines how the command sudo is managed. The `sudo` command allows user to execute commands as the *superuser*.

The file has 4 sections, *User* or *Group* (starts with %), *Hosts*, *User* and *Command*


```bash
# The root can execute on any host (ALL), as any user or group (ALL:ALL), any command (ALL)
root ALL=(ALL:ALL) ALL

# Allows people in group wheel to run all commands
%wheel	ALL=(ALL)	ALL

# user alan may run any command as either user root or bin, optionally setting the group to operator or system.
alan    ALL = (root, bin : operator, system) ALL

# sarah can execute on localhost the shutdown command
sarah localhost=/user/bin/shutdown -r now
```

## Find help

```bash
COMMAND --help


man COMMAND
man SECTION_NUMBER WORD_SEARCH
man man
 
grep -Ri WORD_SEARCH /usr/share/doc/

# update manual pages
mandb

# search in the manual pages
apropos WORD_SEARCH
## if looking for somethig related to DIRECTORIES search for apropos director as this will match directory and directories

info COMMAND

less FILE
```