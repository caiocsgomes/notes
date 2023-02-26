# RHCSA

# Understand and use essential tools for handling files, directories, command-line environments, and documentation

## Files

Commands 

```bash
ls -lha
ls -lha /var/

pwd

cd
cd -

touch FILE

mkdir DIRECTORY

cp SOURCE DESTINATION
cp -r SOURCE DESTINATION # cp -r sourcefolder/ destfolder/

mv SOURCE DESTINATION
mv FILE FOLDER/ # keep same name
mv FILE NEW_FILE

rm FILE
rm -r FOLDER/

find FOLDER -name word

stat FILE or FOLDER

```

### Permissions

```bash
# change group
chgrp GROUP FOLDER_OR_FILE

# change owner
chown USER:GROUP FILE_OR_FILE

# change permissions
# UGO r -> 4, w -> 2, x -> 1
chmod UGO (XXX) file
chmod UGO (XXX) folder
chmod -R UGO (XXX) folder # adds permissions to the folder and recursively to files inside it
chmod u+w file
chmod o-x file
chmod g=r file
chmod g=rw file
chmod g= file # no permissions
chmod u+rw,g=r,o=r file # no permissions

# SUID, SGID-> these allow executables to always execute as a UGO instead of the user permissions
chmod 4600 file # Set Owner User ID on the user
chmod 2600 file # Set Group User ID on the user

# stickybit -> allows only the onwer or root user to delete or rename the affected folder
chmod 1XXX folder
chmod +t folder
```

### Search
```bash
# find [PATH] [SEARCH PARAMETERS]
find /usr/share/ -name '*.jpg'

# c bytes, k kilobytes, M megabytes, G gigabytes
find /usr/ -size +10M # bigger than 10M
find /usr/ -size 10G 
find /usr/ -size -10k # smaller than 10k

find /dev/ -mmin -1 # modified 1 minute ago
find /dev/ -mmin -1 # modified until 1 minute ago
find /dev/ -mmin +1 # modified before 1 minute ago
find /dev/ -mtime 0 # modified until 1 day ago
find /dev/ -mtime 1 # modified between 24h and 48h ago

find . -name file1.txt

find . -iname file1.txt # case insensitive

find . -name 'f*'

# OR
find . -name 'f*' -o -size -10k

# not
find -not -name "f*"

find -perm 664
find -perm -664 # at least these permissions
find -perm /664 # any of these permissions
```

## Inodes and links

Inodes are data structures used to store data about files or folder, they store where the data is stored on disk and are created together with files and folders. When a file or folder are accessed the OS looks up the inode for the file or folder to discover where the block of data is stored on disk. The filesystem stored the inode number for each file, so when a file is open the OS know which block of data to access. The permissions are stored in the inode.

Hard links point to the same inode. To create one:

```bash
ln /path/to/original/file /path/to/soft/link
```

Hard links operate only on files in the same filesystem.

Data in an inode is deleted when no link is pointing to it.

A soft link points to a file (path) instead of an inode, so if the original file is deleted the soft link will be broken. To create one:

```bash
$ ln -s /path/to/original/file /path/to/soft/link
```

Hard links can operate in files and folder in different filesystems.

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