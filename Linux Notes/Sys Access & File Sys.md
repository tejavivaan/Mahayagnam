## What is Root ?
- There are 3 types of root on linux system

-  **Root Account**  is the administrator (super user) of the system. It can modify any file, install software, change settings, and override permissions.
   -  You can become root using **sudo -i** or **su -** 
- **Root Directory /**  is the top most directory of the linux file system.
   - Represented by a single **/**
   - Every file and folder branches from **/**
- **Root home directory**  /root is the personal home folder of the root user.

## How to change Password in Linux ?
- Change Your own password - **passwd**
- Change other user password - **sudo passwd username**
- Change root password - **sudo passwd root**

## If Terminal becomes unresponsive ?
- *Ctrl + C* - Interrupts the current command.
- *Ctrl + D* - Logs out / ends input.
- *Ctrl + Z* - Suspends a running process.

## File System Structure and its Description 
- In Linux, the file system follows a standardized hierarchical structure called the Filesystem Hierarchy Standard (FHS). Everything starts from the root directory /.
  - / - Root directory — the top-level directory in Linux. Everything begins here.
  - /boot - Contains file that is used by the boot loader(grub.cfg).
  - /root - root user home directory.
  - /dev - system devices files (disk, cdrom, speakers, keyboard).
  - /etc - configuration files.
  - /bin - Essential user commands like ls, cp, mv, cat.
  - /sbin - System administration commands like fdisk, reboot, iptables.
  - /opt - Optional third-party software packages.(not part of OS apps)
  - /proc - Running processes.
  - /lib - Essential shared libraries needed by system programs.
  - /tmp - Temporary files created by programs.
  - /home - Home directories for normal users.
  - /var - system log files.
  - /run - Runtime process information since system boot.
  - /mnt - Temporary mount directory used manually by administrators.
  - /media - Mount points for removable media like USB drives and CDs.
 
 ## File System Navigation Commands
  - pwd - prints current working directory.
  - ls - list the files in current directory.
  - cd - changes your current directory.
  - mkdir - creates a new directory.
  - rmdir - removes empty directory.
  - rm -r - removes directories and their contents recursively.
  - touch - creates an empty file.
  - cp - copy files.

  ## Files and Directories Properties
  - Linux files and directories have properties that define  what they are, who owns them, and what actions users can perform on them. The most important properties are file type, permissions, ownership, timestamps, and special/extended attributes

- ls -l is a Linux command that shows detailed information (Properties) about files and directories in a folder.
- It gives you: File type, Permissions, Number of links, Owner, Group, Size, Last modified date, File name.
- Example output of ls -l
> -rwxr-xr--  1  root  admin   4096  Jan 12  10:30  script.sh
- Breakdown of each field
  1. File Types & Permissions *-rwxr-xr--*
   
     + File Type (1st character)
        - *-* → regular file
        - d → directory
        - l → link
        - c → character device
        - b → block device
     + Permissions (next 9 characters)
        - Split into 3 groups:
          
         | Who	  | Example |	Meaning            |
         |---    |---      |---                  |
         | Owner |	rwx	| read, write, execute|
         | Group |	r-x   |	read, execute      |
         | Others|   r--   |	read only          |
   2. Link Count (1)
      - Shows how many hard links point to this file. For directories, this number is usually higher.
   3. Owner (root)
      - The user who owns the file.
   4. Group (admin)
      - The group that owns the file.
   5. File Size (4096)
      - Size in bytes.For directories, this is the size of directory metadata.
   6. Last Modified Time (Jan 12 10:30)
      - Shows when the file was last changed. If the file is older than 6 months, the year is shown instead of time.
   7.  File Name (script.sh)  
      -  The name of the file or directory. 

