# Bash Cheat Sheet

## Basic Navigation

| Action                     | Command                           |
|----------------------------|-----------------------------------|
| Print working directory    | `pwd`                             |
| List files (long format)   | `ls -l`                           |
| Change directory           | `cd /path/to/directory`           |
| Go up one directory        | `cd ..`                           |
| Go to home directory       | `cd ~`                            |

## File Management

| Action                              | Command                           |
|-------------------------------------|-----------------------------------|
| Copy a file                         | `cp source.txt destination.txt`   |
| Copy a directory recursively        | `cp -r sourcedir targetdir`       |
| Move or rename a file               | `mv oldname.txt newname.txt`      |
| Remove a file                       | `rm file.txt`                     |
| Remove a directory recursively      | `rm -r directory/`                |
| Create a directory                  | `mkdir newfolder`                 |
| Create an empty file                | `touch newfile.txt`               |

## Viewing & Searching Files

| Action                             | Command                                    |
|------------------------------------|--------------------------------------------|
| Show file contents                 | `cat file.txt`                             |
| Page through a file                | `less file.txt`                            |
| Show first 10 lines (head)         | `head file.txt`                            |
| Show last 10 lines (tail)          | `tail file.txt`                            |
| Search in a file                   | `grep "search_term" file.txt`              |
| Recursive search                   | `grep -r "search_term" /path/to/dir/`      |

## Permissions

| Action                      | Command                          |
|-----------------------------|----------------------------------|
| Change file permissions     | `chmod 755 script.sh`            |
| Change file owner           | `sudo chown user:group file.txt` |

## Useful Shortcuts

| Action                     | Shortcut                  |
|----------------------------|---------------------------|
| Show command history       | `history`                |
| Run last command again     | `!!`                     |
| Autocomplete               | Press `TAB`              |
| Cancel current command     | Press `Ctrl+C`           |
| Exit shell                 | `exit`                   |

## Variables & Scripts

| Action                     | Command                     |
|----------------------------|-----------------------------|
| Set a variable             | `MYVAR="value"`             |
| Print a variable           | `echo "$MYVAR"`             |
| Run a script               | `bash script.sh`            |
| Make a script executable   | `chmod +x script.sh`        |

## Networking

| Action                 | Command                          |
|------------------------|----------------------------------|
| Show IP address        | `ip a` or `ifconfig`             |
| Ping a host            | `ping 8.8.8.8`                   |
| Download a file (wget) | `wget http://example.com/file.zip` |

## Process Management

| Action                   | Command                        |
|--------------------------|--------------------------------|
| Show running processes   | `ps aux`                       |
| Find a process           | `ps aux \| grep processname`   |
| Kill a process by PID    | `kill 1234`                    |
| Kill all processes by name | `killall processname`        |

## Disk Usage

| Action                            | Command                    |
|-----------------------------------|----------------------------|
| Show disk usage for files/folders | `du -sh *`                 |
| Show free disk space              | `df -h`                    |

## Other Useful Commands

| Action                         | Command                                       |
|--------------------------------|-----------------------------------------------|
| Show environment variables     | `printenv`                                    |
| Find files by name             | `find . -name "filename.txt"`                 |
| Show current date/time         | `date`                                        |

## Advanced Bash

### Command Chaining

| Action                            | Command                               |
|-----------------------------------|---------------------------------------|
| Run commands if previous succeeds | `command1 && command2`                |
| Run commands if previous fails    | `command1 || command2`                |
| Run commands sequentially         | `command1 ; command2`                 |

### Redirection & Pipes

| Action                            | Command                               |
|-----------------------------------|---------------------------------------|
| Redirect stdout to file           | `echo "Hello" > file.txt`            |
| Append stdout to file             | `echo "World" >> file.txt`           |
| Redirect stderr to file           | `command 2> error.log`               |
| Redirect stdout & stderr to file  | `command > out.log 2>&1`             |
| Pipe output to another command    | `cat file.txt \| grep "pattern"`     |

### Loops

| Action               | Command                                              |
|----------------------|------------------------------------------------------|
| For loop             | `for i in {1..5}; do echo "Number $i"; done`         |
| While loop           | `while read line; do echo "$line"; done < file.txt`  |

### Conditionals

| Action       | Command                                                                    |
|--------------|----------------------------------------------------------------------------|
| If statement | `if [ -f file.txt ]; then echo "file exists"; else echo "file not found"; fi` |

### Functions

| Action                     | Command                                                             |
|----------------------------|---------------------------------------------------------------------|
| Define and call a function | <pre>greet() {<br>  echo "Hello, $1!"<br>}<br>greet "Ewan"</pre>     |

### Find & Xargs

| Action                     | Command                                             |
|----------------------------|-----------------------------------------------------|
| Delete all `.log` files    | `find . -name "*.log" -type f -delete`              |
| Find and run a command     | `find . -name "*.txt" \| xargs cat`                 |

### Sed & Awk

| Action                                | Command                                  |
|---------------------------------------|------------------------------------------|
| Replace text in-place                 | `sed -i 's/oldtext/newtext/g' file.txt` |
| Print the second column from a file   | `awk '{print $2}' file.txt`             |

### Tar & Gzip

| Action                        | Command                            |
|-------------------------------|------------------------------------|
| Create a tar.gz archive       | `tar -czvf archive.tar.gz folder/` |
| Extract a tar.gz archive      | `tar -xzvf archive.tar.gz`         |

### SSH & Rsync

| Action                       | Command                                       |
|------------------------------|-----------------------------------------------|
| SSH into a server            | `ssh user@host`                               |
| Copy files to a remote host  | `scp file.txt user@host:/path/`               |
| Sync directories             | `rsync -avz source/ user@host:/dest/`         |

## Script Template

| Action            | Template                                      |
|-------------------|-----------------------------------------------|
| Basic shell script| <pre>#!/bin/bash<br>echo "This is a shell script"</pre> |

## Miscellaneous

| Action                               | Command             |
|--------------------------------------|---------------------|
| Print last command's exit code       | `echo $?`           |
| Get number of files in a directory   | `ls \| wc -l`       |
| Generate a random number             | `echo $RANDOM`      |
| Sleep for 5 seconds                  | `sleep 5`           |

**Tip:** Use `man <command>` to view the manual for any command!