# Truncate File Size
- **truncate** is used to shrink or extend the size of a file to a specific size.
- If the file is larger, truncate cuts the extra data.
- If the file is smaller, truncate adds null bytes to increase its size.
- Basic Syntax: ***truncate -s SIZE filename***
- -s = size you want the file to become.
- You can specify size in:
    - Bytes → 100
    - Kilobytes → 100K
    - Megabytes → 10M
    - Gigabytes → 1G
      
- Create an empty file - ***truncate -s 0 file.txt***
    - This clears the file (same as > file.txt).
- Shrink a file to 1 KB - ***truncate -s 1K logfile.txt***
    - Cuts the file down to 1024 bytes.
- Extend a file to 10 MB - ***truncate -s 10M testfile.bin***
    - If the file is smaller, null bytes are added.
- Create a new file of fixed size - ***truncate -s 5M dummy.img***
    - Creates a 5 MB file — useful for testing storage.
- Reduce file by 50 bytes - ***truncate -s -50 file.txt***
    - Removes the last 50 bytes.
- Increase file by 1 MB - ***truncate -s +1M file.txt***
    -  Adds 1 MB of null bytes.

- **Important Notes for Beginners**
    - Truncate does not ask for confirmation — be careful.
    - Shrinking a file permanently deletes the removed data.
    - Extending a file adds null characters, not readable text.
    - Works only on regular files, not directories.
