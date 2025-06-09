# Bash Cheat Sheet (Basic + Advanced)

## Basic Navigation

**Print working directory**
```bash
pwd
```

**List files (long format)**
```bash
ls -l
```

**Change directory**
```bash
cd /path/to/directory
```

**Go up one directory**
```bash
cd ..
```

**Home directory**
```bash
cd ~
```

---

## File Management

**Copy a file**
```bash
cp source.txt destination.txt
```

**Copy a directory recursively**
```bash
cp -r sourcedir targetdir
```

**Move or rename a file**
```bash
mv oldname.txt newname.txt
```

**Remove a file**
```bash
rm file.txt
```

**Remove a directory recursively**
```bash
rm -r directory/
```

**Create a directory**
```bash
mkdir newfolder
```

**Create an empty file**
```bash
touch newfile.txt
```

---

## Viewing and Searching Files

**Show file contents**
```bash
cat file.txt
```

**Page through a file**
```bash
less file.txt
```

**Head (first 10 lines)**
```bash
head file.txt
```

**Tail (last 10 lines)**
```bash
tail file.txt
```

**Search in a file**
```bash
grep "search_term" file.txt
```

**Recursive search**
```bash
grep -r "search_term" /path/to/dir/
```

---

## Permissions

**Change file permissions**
```bash
chmod 755 script.sh
```

**Change file owner**
```bash
sudo chown user:group file.txt
```

---

## Useful Shortcuts

**Command history**
```bash
history
```

**Run last command again**
```bash
!!
```

**Autocomplete command or filename**
```
[TAB]
```

**Cancel current command**
```
Ctrl+C
```

**Exit shell**
```bash
exit
```

---

## Variables & Scripts

**Set a variable**
```bash
MYVAR="value"
```

**Print variable**
```bash
echo "$MYVAR"
```

**Run a script**
```bash
bash script.sh
```

**Make a script executable**
```bash
chmod +x script.sh
```

---

## Networking

**Show IP address**
```bash
ip a
```
or
```bash
ifconfig
```

**Ping a host**
```bash
ping 8.8.8.8
```

**Download a file (wget)**
```bash
wget http://example.com/file.zip
```

---

## Process Management

**Show running processes**
```bash
ps aux
```

**Find a process**
```bash
ps aux | grep processname
```

**Kill a process by PID**
```bash
kill 1234
```

**Kill all processes by name**
```bash
killall processname
```

---

## Disk Usage

**Show disk usage for all files/folders**
```bash
du -sh *
```

**Show free disk space**
```bash
df -h
```

---

## Other Useful Commands

**Show environment variables**
```bash
printenv
```

**Find files by name**
```bash
find . -name "filename.txt"
```

**Show current date/time**
```bash
date
```

---

## Advanced Bash

### Command Chaining

**Run commands in sequence**
```bash
command1 && command2  # Only runs command2 if command1 succeeds
command1 || command2  # Runs command2 if command1 fails
command1 ; command2   # Runs both commands regardless of success/failure
```

### Redirection & Pipes

**Redirect output to a file**
```bash
echo "Hello" > file.txt   # Overwrites
echo "World" >> file.txt  # Appends
```

**Redirect stderr**
```bash
command 2> error.log
```

**Redirect stdout and stderr**
```bash
command > out.log 2>&1
```

**Pipe output to another command**
```bash
cat file.txt | grep "pattern"
```

### Loops

**For loop**
```bash
for i in {1..5}; do
  echo "Number $i"
done
```

**While loop**
```bash
while read line; do
  echo "$line"
done < file.txt
```

### Conditionals

**If statement**
```bash
if [ -f file.txt ]; then
  echo "file exists"
else
  echo "file not found"
fi
```

### Functions

**Define and use a function**
```bash
greet() {
  echo "Hello, $1!"
}
greet "Ewan"
```

### Find & Xargs

**Delete all `.log` files**
```bash
find . -name "*.log" -type f -delete
```

**Find and run command**
```bash
find . -name "*.txt" | xargs cat
```

### Sed & Awk

**Replace text in a file (in-place)**
```bash
sed -i 's/oldtext/newtext/g' file.txt
```

**Print the second column from a file**
```bash
awk '{print $2}' file.txt
```

### Tar/Gzip

**Create a tar.gz archive**
```bash
tar -czvf archive.tar.gz foldername/
```

**Extract a tar.gz archive**
```bash
tar -xzvf archive.tar.gz
```

### SSH & Rsync

**SSH into a server**
```bash
ssh user@host
```

**Copy files to a remote server**
```bash
scp file.txt user@host:/path/
```

**Sync directories**
```bash
rsync -avz source/ user@host:/dest/
```

---

## Script Template

**Basic shell script**
```bash
#!/bin/bash
echo "This is a shell script"
```

---

## Miscellaneous

**Print the last command's exit code**
```bash
echo $?
```

**Get the number of files in a directory**
```bash
ls | wc -l
```

**Generate a random number**
```bash
echo $RANDOM
```

**Sleep for 5 seconds**
```bash
sleep 5
```

---

**Tip:** Use `man <command>` to view the manual for any command!