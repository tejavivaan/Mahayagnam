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
- ***Ctrl + C*** - Interrupts the current command.
- ***Ctrl + D*** - Logs out / ends input.
- ***Ctrl + Z*** - Suspends a running process.

## File System Structure and its Description 
- In Linux, the file system follows a standardized hierarchical structure called the Filesystem Hierarchy Standard (FHS). Everything starts from the root directory /.
  - ***/*** - Root directory — the top-level directory in Linux. Everything begins here.
  - ***/boot*** - Contains file that is used by the boot loader(grub.cfg).
  - ***/root*** - root user home directory.
  - ***/dev*** - system devices files (disk, cdrom, speakers, keyboard).
  - ***/etc*** - configuration files.
  - ***/bin*** - Essential user commands like ls, cp, mv, cat.
  - ***/sbin*** - System administration commands like fdisk, reboot, iptables.
  - ***/opt*** - Optional third-party software packages.(not part of OS apps)
  - ***/proc*** - Running processes.
  - ***/lib*** - Essential shared libraries needed by system programs.
  - ***/tmp*** - Temporary files created by programs.
  - ***/home*** - Home directories for normal users.
  - ***/var*** - system log files.
  - ***/run*** - Runtime process information since system boot.
  - ***/mnt*** - Temporary mount directory used manually by administrators.
  - ***/media*** - Mount points for removable media like USB drives and CDs.
 
 ## File System Navigation Commands
  - ***pwd*** - prints current working directory.
  - ***ls*** - list the files in current directory.
  - ***cd*** - changes your current directory.
  - ***mkdir*** - creates a new directory.
  - ***rmdir*** - removes empty directory.
  - ***rm -r*** - removes directories and their contents recursively.
  - ***touch*** - creates an empty file.
  - ***cp*** - copy files.

## Files and Directories Properties
  - Linux files and directories have properties that define  what they are, who owns them, and what actions users can perform on them. The most important properties are file type, permissions, ownership, timestamps, and special/extended attributes

- ls -l is a Linux command that shows detailed information (Properties) about files and directories in a folder.
- It gives you: File type, Permissions, Number of links, Owner, Group, Size, Last modified date, File name.
- Example output of ls -l
- ***-rwxr-xr--  1  root  admin   4096  Jan 12  10:30  script.sh***
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

## Types of Paths in Linux
- Absolute Path
   - A path that starts from the root / and shows the full location of a file.
- Relative Path
   - A path based on your current directory. Relative paths do NOT start with /
 
## Creating Files and Directories in Linux
- Linux gives you several commands to create files and folders. Each command has a different purpose.
- **mkdir** — Make a new directory
   - ***mkdir myfolder*** - Creates a folder named myfolder in the current location.
   - ***mkdir folder1 folder2 folder3*** - Create multiple folders
   - ***mkdir -p projects/java/src*** - Create nested directories,-p creates parent directories automatically.
- **touch** — Create an empty file
   -  ***touch file1.txt*** - cretas file1.txt
   -  ***touch a.txt b.txt c.txt*** - Create multiple files
   -  ***touch report.log*** - Update timestamp of an existing file
- **echo** — Create a file with content
   -  ***echo "Hello Linux" > hello.txt*** - Creates hello.txt and writes text inside it.
   -  ***echo "New line" >> hello.txt*** - Append text to hello.txt

## Copying a Directory in Linux
- To copy a directory, we use the cp command with the -r (recursive) option.
- Basic Command to Copy a Directory.
  - ***cp -r source_directory destination_directory***
  - ***cp -r myfolder backup/*** - This copies myfolder into the backup directory. 
- Copy a Directory to Another Location.
  - ***cp -r /home/user/docs /home/user/Desktop/*** -  This copies the docs folder to the Desktop.
- Copy a Directory and Rename It.
  - ***cp -r project project_backup*** - This creates a new directory named project_backup.
- Copy Multiple Directories at Once.
  - ***cp -r dir1 dir2 dir3 /home/user/backup/*** - All three directories go into backup.

## Finding Files and Directories
- Linux gives you powerful commands to search for files and directories anywhere in the system. The two most important tools are:
   - find — searches by location
   - locate — searches using a database (very fast)
     
### Find command
- The find command searches in real time by scanning directories.
   - ***find path condition***
- Find a file by name
    - ***find / -name "filename.txt"***
- Case Insensitive search
    - ***find / -iname "myfile.txt"***
    - **-iname** ignores uppercase/lowercase
- Find a Directory
   -  ***find /home -type d -name "Documents"***
   -  **-type d** → directory
   -  **-type f** → file
- Find by file extension
   - ***find . -name "*.sh"***
   - **.** → current directory
   - **"*.sh"** → all shell scripts
- Find files bigger than a size
    - ***find / -size +100M***
 - Find empty files or folders
    - ***find . -empty***

### Loacte command 
- locate is much faster than find because it uses a pre‑built database.
- install if missing - ***sudo apt install mlocate*** & ***sudo apt updatedb***
- Search for a file
  - ***locate notes.txt***
- Search by partial name
    - ***locate doc***
- Search for a directory
     - ***locate /home/user/Documents***
  
 
## Wildcards
- Wildcards are special symbols that help you match multiple files or patterns without typing full names.
- They are used in commands like ls, cp, rm, mv, find, etc.
    - "*" → “anything, any length”
    - ? → “one unknown character”
    - [abc] → “one of these”
    - [1-9] → “one from this range”
    - [!x] or [^x] → “anything except this”

## File Types in Linux
- Regular file (-) — Text, images, programs, logs, etc.
- Directory (d) — A folder containing files.
- Symbolic link (l) — Shortcut pointing to another file.
- Character device (c) — Hardware that sends data character by character (keyboard, mouse).
- Block device (b) — Hardware that sends data in blocks (hard disks, USB drives).
- Socket (s) — Used for inter‑process communication.
- Named pipe (p) — Allows processes to communicate in a FIFO manner.

### Soft Link (Symbolic Link)
- A soft link is like a shortcut or pointer to another file
- It stores the path of the original file.
- If the original file is deleted → link breaks
- File type shown as	l
- ***ln -s target linkname***

### Hard Link
- A hard link is an additional name for the same file.
- It points directly to the same data (inode) as the original file.
- If the original file is deleted → data still exists via the link 
- File type shown as	 -
- ***ln target linkname***





