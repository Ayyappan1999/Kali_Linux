# etc in Linux

* In linux `etc` is stands for `Editable Text Configuration`.
* It is a root directory of file system and contains various system configuration files.
* This directory contains system-wide configuration files that are used by various applications and process running on a system.
* some of the important files in  `/etc` directory inclues
```
        1. /etc/passwd
        2. /etc/shadow
        3. /etc/group
        4. /etc/fstab
        5. /etc/apt/sources.list
        6. /etc/hostname
        7. /etc/hosts
```

### 1. /etc/passwd

* Contains information about the user accounts on the system.

```
Eg:
    ayyappan:x:1000:1000:ayyappan,,,"/home/ayyappan:/usr/bin/zsh
    
    i.   ayyappan                     -> name of the user account
    ii.  x                            -> An encrypted password or an "x" character indicates that the password is stored in the `etc/shadow ` folder
    iii. 1000                         -> user id, an unique numeric identifier assigned to each user account
    iv.  1000                         -> group id (primary) numeric identifier assigned to primary group of the user
    v.   ayyappan,,,                  -> Contains additional information about user, such as full name or contact information
    vi.  /home/ayyappan               -> Path of the user's home directory
    vii. /usr/bin/zsh                 -> PAth to z-shell, the program that is run when the user logs in
```

### 2. /etc/shadow

* Contains the encrypted passwords for the user accounts on the system

```
Eg:
    ayyappan:$..$..:19381:0:99999:7:::

    i.   ayyappan             -> name of the user (user account).
    ii.  $....$....           -> encrypted password for ayyappan. This is a SHA-512 hash of ayyappan's password with a salt value.
                                 Note: Salt value is UNIQUE.
                                 ! : if exclamatory symbol exists, No password is created.
    iii. 19381                -> The date if last password changed, represented as No. of days since january 1, 1970.
    iv.  0                    -> The minimum no of days that must elapse between password changes.
    v.   99999                -> The maximum no of days that a password can used before it must be changed.
    vi.  7                    -> The no of days before a password expires that the user should be warned to change it.
    vii. : : :                -> The password is inactive & account expiration fields are not set for root account.   
```

### 3. /etc/group

* Contains information about the group on the system

```
Eg:
    admins:x:1000:jane,john

    i.   admins          -> group name
    ii.  x               -> encrypted password
    iii. 1000            -> group id
    iv.  jane, john      -> 2 members
```

### 4. /etc/apt/sources.list

* Contains the list of software repositories that the system user to download and install the packages.
* APT : Advanced Package Tool
* Component(s): Specifies the components or sections of the repository (e.g., "main", "contrib", "non-free") that contain packages.
* main : Supported by KALI
* non-free, contrib : Not supported but available for install  

### 5. /etc/fstab

* Contains information about the file systems that are mounted at boot time.
```
1. Device or UUID: Specifies the device or partition to be mounted. It can be a device file (e.g., /dev/sda1) or a Universally Unique Identifier (UUID).
2. Mount point: Specifies the directory where the file system should be mounted.
3. File system type: Specifies the file system type (e.g., ext4, ntfs, nfs).
4. Mount options: Specifies additional mount options, such as read-only (ro), read-write (rw), permissions (uid, gid), and others.
5. Dump: Used by the dump command to determine if the file system needs to be backed up (0 means no backup, 1 means backup).
6. Pass: Used by the fsck command to determine the order in which file systems should be checked (0 means no check, 1 means root file system, higher numbers indicate other file systems).
```

### 6. /etc/hostname

* It stores the hostname of the local system.
* The hostname is a label or identifier assigned to a device on a network, typically used for identification and communication purposes.

### 7. /etc/hosts

* Contains IP address and hostname of the other system on network.
* IP : Numerical ip address of the host
* Hostname: Name of the host associated with the IP Address

Eg:
-> 127.0.0.1 idva.diva
-> `/etc/hosts` file is used by system to provide quick resolution of domain names on local network without the need of DNS Server.
