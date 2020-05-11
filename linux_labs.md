# Linux labs <!-- omit in toc -->

Summary of commands of the Rangeforce labs.

- [Users](#users)
  - [User data](#user-data)
  - [User passwords](#user-passwords)
  - [User groups](#user-groups)
- [Files](#files)
  - [Managing files and folders](#managing-files-and-folders)
  - [File and folder permissions](#file-and-folder-permissions)
  - [Special permissions](#special-permissions)
  - [File and folder ownership](#file-and-folder-ownership)
- [Disks](#disks)
  - [Partition creation](#partition-creation)
  - [Swap area](#swap-area)
  - [Partition mounting](#partition-mounting)
  - [Automating mounting](#automating-mounting)

## Users

Login via ssh

```sh
ssh username@address
```

Become root

```sh
sudo -i
# OR
su
```

To check your user

```sh
whoami
```

To switch your user

```sh
su - <username>
```

### User data

Creating a user

```sh
adduser <username>
```

Check user creation outcome: shows user ID, group ID and list of user groups

```sh
id <username>
```

User IDs

- `0` is reserved for `root`
- `0 - 99` are for system Users
- `199 - 999` are for special use / system users
- `1000 - ...` are for ordinary users

Get user's default shell

```sh
getent passwd <username>
```

Modify user data using `usermod` and parameters

```sh
usermod -s /bin/dash <username>
```

Removing a user

```sh
deluser --remove-home <username>
```

### User passwords

Check account password status. `L` stands for locked. `P` shows enabled.

```sh
passwd -S <username>
```

Lock a user's account

```sh
passwd -l <username>
# Display
passwd: password expiry infoamtion changed.
```

Unlocking a user

```sh
passwd -u <username>
```

### User groups

Creating a group

```sh
addgroup <groupname>
```

Getting info about a group

```sh
getent group <groupname>
```

Adding users to a group

```sh
adduser <username> <groupname>
```

Viewing an user's groups

```sh
id <username>
# OR
groups <username>
```

Removing users from a group

```sh
deluser <username> <groupname>
```

Removing a group

```sh
delgroup <groupname>
```

## Files

To get more info about a command

```sh
man <commandname>
```

### Managing files and folders

Creating a folder

```sh
mkdir <path/foldername>

# For root folders:
mkdir /foldername
```

Fiding and filtering files

```sh
find <path> -name '*<match>*' 2>/dev/null
# 2>/dev/null discards error messages
# use / as path for global search
```

To find and move

```bash
find <path> -name '*<match>*' -exec mv {} <dest_path> \;
```

### File and folder permissions

Managing file folder permissions

```sh
chmod <permsint> <target>

# Numerical
chmod ___ <target>

# Alphabetical, - for removing, + for adding
chmod u_, g_, o_
```

Creating a script

```sh
nano <path/filename>.sh
```

Example of a backup script

```bash
#!/bin/bash
echo "Copy original files to backup folder"
cp -aR /uploads / backup
cp -aR /etc /backup
echo "Create a tar archive of backed up files
tar -czvf uploads backup_backup.tar.gz /backup/uploads > /dev/null 2>&1
tar -czvf etc_backup.tar.gz /backup/etc > /dev/null 2>&1
```

### Special permissions

- **sticky bit**: used in `/tmp` so that all users can save files, but only owner can delete the file | `o+t` or `1`
- **setUID bit**: can oly be set on a file, and if the file can be executed as root, then all users can execute it as root | `u+s` or `4`
- **setGID bit**: can be set on files and folders and causes group permission inheritance | `g+s` or `2`

Changing group of a folder and subfolders

```sh
chgrp <groupname> <path> -R
```

Finding files with permissions

```sh
find <path> -perms <permsint> 2>dev/null
# For setUID: 4755
# For sticky: 1777
```

### File and folder ownership

Change owner of a file / folder

```sh
chown <username> <path> [-R]
# R stands for recursive for groups
```

Change group of a file / folder

```sh
chgrp <groupname> <path> [-R]
```

## Disks

To display all existing block devices

```sh
lsblk
```

To _select_ a disk

```sh
fdisk [disk]
```

### Partition creation

- `n` option for new partition
- `w` option for writing and exiting

### Swap area

Creating a new swap area

```sh
mkswap <device>
```

Enabling or disabling swap area

```sh
swapon
wapoff
# -s shows target areas
# -a selects all areas
```

Changing permanent swappiness setting

```sh
sysctl vm.swappiness
```

Swappiness settings can be checked with

```sh
cat /proc/sys/vm/swappiness
```

Making changes permanent

```sh
sysctl vm.swappiness=<option> >> /etc/sysctl.conf
```

Checking permanent changes

```sh
cat /etc/sysctl.conf | grep swap
```

### Partition mounting

Creating a file system on a disk

```sh
mkfs
# Use -t to specify the filesystem
# OR
mkfs.<filesystem> <device>
```

Getting info about formatted partitions

```sh
blkid
# OR
lsblk -f
```

Mounting and unmounting partitions

```sh
mount
unmount
# use {name1, name2, ...} to specify folders to mount / unmount
```

Displaying all mounted partitions

```sh
df -h
```

### Automating mounting

Automatically enabling swap

```sh
blkid | grep <partition> >> /etc/fstab
nano /etc/fstab
# Then, comment out unnecessary info
```

`fstab` for swap

```sh
<filesystem>  <mountpoint> <type> <options> <dump> <pass>
UUID=... none swap sw 0 0
```

`fstab` for regular partitions

```sh
UUID=... /mnt/<mountpoint> {ext4 | ntfs} defaults 0 2
```
