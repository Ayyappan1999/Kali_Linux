# KALI LINUX
* Kali Linux is a specialized Linux distribution that is focused on penetration testing, digital forensics, and network security auditing.
* It is widely used by cybersecurity professionals, ethical hackers, and researchers for assessing and securing computer systems.
* Kali Linux is based on Debian and is designed to provide a comprehensive set of tools and utilities for various security-related tasks.
* It includes a vast collection of pre-installed software and packages that are specifically tailored for penetration testing and security auditing purposes.

## KERNEL
* In Linux, the kernel refers to the core component of the operating system.
* It is responsible for managing system resources, providing an interface for applications to interact with hardware and ensuring the overall stability and security of the system.
* The Linux kernel acts as an intermediary between the hardware and the software running on a Linux-based system.
* It handles tasks such as process management, memory management, device driver management, file system access, and network communication.

## SHELL
* In the context of computing, a shell refers to a program or interface that provides a way for users to interact with an operating system.
* It acts as a command-line interpreter, allowing users to execute commands, run programs, and manage the system through textual commands.
* A shell provides a command-line interface (CLI) where users can enter commands and receive output in the form of text.
* It interprets these commands and interacts with the operating system to carry out the requested actions.
* In the Unix-like operating systems, including Linux, there are several shells available, with the most common ones being Bash (Bourne Again SHell), Zsh (Z Shell), and Fish (Friendly Interactive SHell).
* Each shell has its own set of features, syntax and capabilities.

## File Management - Commands


Sure! Here's a table view of some commonly used file management commands in Linux:

| Command | Description |
|---------|-------------|
| `ls` | List files and directories in the current directory |
| `cd` | Change directory |
| `pwd` | Print the current working directory |
| `mkdir` | Create a new directory |
| `rmdir` | Remove an empty directory |
| `cp` | Copy files and directories |
| `mv` | Move or rename files and directories |
| `rm` | Remove files and directories |
| `cat` | Display the contents of a file |
| `less` | View file contents one page at a time |
| `head` | Display the beginning of a file |
| `tail` | Display the end of a file |
| `touch` | Create an empty file or update the timestamp of an existing file |
| `chmod` | Change the permissions of a file or directory |
| `chown` | Change the owner of a file or directory |
| `chgrp` | Change the group ownership of a file or directory |
| `find` | Search for files and directories |
| `grep` | Search for text patterns within files |
| `ln` | Create a hard or symbolic link to a file or directory |
| `stat` | Display file or file system status |
| `file` | Determine file type |
| `more` | Displays the contents of a file one screen at a time |
| `nano` | create a new file and edit in terminal itself |
| `echo` | simply outputs the provided text or the value of variables to the standard output |
| `whatis` | Get detailed information about the commands |

* The ls command is one of the most basic and commonly used commands in Kali Linux.

* `-a` : Lists all files, including hidden files.
* `-l` : Lists files in long format, which includes the file permissions, owner, group, size, and modification time.
* `-r` : Lists files in reverse order.
* `-t` : Lists files in order of modification time.
* `ls -lh` : Lists files in long format, including the file permissions, owner, group, size, and modification time, and human-readable file sizes.
* `ls -al` : Lists all files, including hidden files in long format.
* `ls -R` : Lists the contents of a directory recursively, meaning that it will list the contents of all subdirectories as well.
* `ls -F` : Appends a character to each file name to indicate its type.

## Permission Management

1. rwx
```
                     Permission
                         ↓
              -----------------------
              ↓          ↓          ↓
              r          w          x
```
`read (r)`
* Permission is provide only to read a file
* Numerical value for read permission is 4
* r = 4

`write (w)`
* A Person can able to edit, add, remove or rename the file or a directory
* Numerical value for write permission is 2
* w = 2

`execute (x)`
* A person can able to run a file and traverse(access) a directory
* Numerical value for execute permission is 1
* x = 1

[rwx  rwx  rwx]
  ↓    ↓    ↓
  u    g    o

where
* u => user or owner
* g => group
* o => others
* a => all

2. chmod
* The chmod command in Linux is used to change the permissions of files and directories.
* It allows you to modify the read (r), write (w), and execute (x) permissions for the owner, group, and others.
```
* There are two ways to modify a files or directories
  i.  By Numbers
  ii. By Letters 
```

`+` adds the specified permission.
`-` removes the specified permission.
`=` sets the specified permission.
```
Eg:
chmod 755 script.sh           # Sets read, write, and execute permissions for the owner, and read and execute permissions for the group and others
chmod +x script.sh            # Adds execute permission for all user categories
chmod u=rw,g=r,o= file.txt     # Sets read and write permissions for the owner and group, and removes all permissions for others
chmod -R 644 directory/       # Recursively sets read and write permissions for the owner, and read-only permissions for the group and others, for all files and directories within "directory"
```

### Table View
```
----------------------------------------------------------
|    Number     |    Permission Types    |    Symbols    |
----------------------------------------------------------
|    0 (000)    |      No Permission     |      ---      |      
|    1 (001)    |      Execute           |      --x      |
|    2 (010)    |      Write             |      -w-      |
|    3 (011)    |      Execute, Write    |      -wx      |
|    4 (100)    |      Read              |      r--      |
|    5 (101)    |      Read, Execute     |      r-x      |
|    6 (110)    |      Read, Write       |      rw-      |
|    7 (111)    |      Read, Write,      |      rwx      |  
|               |      execute           |               |
----------------------------------------------------------
```

## FILES & DIRECTORIES OWNERSHIP

-------------------------
| Command | Description |
|---------|-------------|
| `chown` | Change the owner of a file or directory |
| `chgrp` | Change the group ownership of a file or directory |
| `ls` | List files and directories with ownership information |
| `id` | Display the current user and group information |
| `whoami` | Show the current user |
| `groups` | List the groups that the current user belongs to |
| `su` | Switch to another user account |
| `sudo` | Execute a command with elevated privileges |
| `adduser` | Create a new user |
| `deluser` | Delete a user |
| `addgroup` | Create a new group |
| `delgroup` | Delete a group |


## BASIC COMMANDS
```
1. grep      -> finding particular words in files
2. locate    -> shows where the file or folder locating
3. grep -i   -> case insensitive
4. |         -> pipe command
```
    eg:
       cat dark.txt | head -> it shows first 10 lines in a text file.
       cat dark.txt | tail -> it shows last 10 lines in a text file.
```
6. man       -> manual
7. less      -> after | type less it shows less content
8. find      -> to search for files and directories within a specified directory hierarchy
```

## SYSTEM & USER INFORMATION

```
1. whoami                 -> display the username of the current user
2. hostname               -> display the username or pc name
3. lsb_release -a         -> OS version name
4. cat /etc/os-release    -> OS release name
5. uname -a               -> it shows linux name
```

## FILE & STORAGE SIZE

```
1. du -sh * -> File Size
2. df -h    -> Drive Size
```

## COMPRESSION

```
-c : create archieves
-x: extract the archieves
-f : create archieve with given filename
-t : display or lists file in archieve file
-u : archieve & adds to an exist archieve file
-v : display verbose info
-A : Concatenate the archieve file
-z : zip, tells tar command that create tar file using gzip
-j : filter archieve tar file using bzip2
-W : verify a archieve file
-r : update or add file to exist .tar file


    Eg:
        1. tar -cvf file.tar file1
        2. tar -xvf file.tar test
        3. tar -czf file.tar.gz test
        4. tar -xzf file.tar.gz test
```

## NETWORK COMMANDS

```
1. ifconfig : configure and display information about network interfaces on a system
2. dhclient : obtain or release an IP address lease from a DHCP (Dynamic Host Configuration Protocol) server
3. systemctl restart network-manager.service :  used in Linux to restart the Network Manager service.
4. netstat -r : display the kernel's IP routing table
5. netdiscover -i eth0 : perform network discovery and identify active hosts on a local network
6. cat /etc/hosts : It is a local text file that maps hostnames to IP addresses
```








