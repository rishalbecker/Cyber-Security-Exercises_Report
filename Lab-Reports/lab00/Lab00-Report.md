# Lab 00 – Introduction to Linux Basics

## 1. Objective
The objective of this lab was to learn basic Linux command-line operations, including navigating directories, creating and managing files, checking permissions, and gathering system information.

## 2. Basic Navigation
Commands practiced:
- `pwd` – displays the current working directory.
- `ls` – lists directory contents.
- `ls -l` – displays files with detailed information.
- `cd` – changes the current directory.

Created and accessed the exercise directory:
`~/linux-exercise`

## 3. File and Directory Management
Commands practiced:
- `mkdir` – creates directories.
- `touch` – creates empty files.
- `echo` – writes text to a file when redirected.
- `cat` – displays file contents.
- `mv` – moves files.

Created `description.txt` containing my name and moved it into the `test` directory.

Verified the file using:
`cat test/description.txt`

## 4. Moving and Copying Files
Commands practiced:
- `mv` – moves or renames files.
- `cp` – copies files.

An existing `my_profile.txt` was present in the test directory and home directory. The copy attempt was blocked because the destination file in the home directory was read-only. The existing files were preserved.

## 5. File Sizes and Permissions
Commands practiced:
- `ls -lh` – lists file sizes in human-readable format.
- `du -sh *` – displays the disk usage of files and directories.
- `chmod` – changes file permissions.

The file `my_profile.txt` was changed to read-only permissions using:
`chmod 444 my_profile.txt`

Verified the permissions using:
`ls -l my_profile.txt`

The resulting permissions were:
`-r--r--r--`

## 6. System Information
Commands practiced:
- `whoami` – identifies the current user.
- `uname -a` – displays system and kernel information.
- `df -h` – displays disk space usage.
- `du -sh ~` – displays the size of the home directory.

Observed results:
- Username: kali
- Operating system: Kali Linux
- Architecture: x86_64
- Root filesystem size: 79 GB
- Available disk space: 56 GB
- Home directory size: 1.1 GB

## 7. Finding Large Files and Directories
Command used:
`du -ah ~ | sort -rh | head -n 5`

This command listed the five largest files or directories in the home directory.

The largest items observed included:
- `/home/kali` – 1.1 GB
- `/home/kali/.cache` – 793 MB
- Firefox cache directory – approximately 785 MB

## 8. Conclusion
This lab provided practical experience with basic Linux terminal commands. I learned how to navigate the filesystem, create and move files, inspect file sizes, change permissions, retrieve system information, and identify large directories.

