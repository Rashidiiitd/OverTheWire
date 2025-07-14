## FIND-GUIDE 

find [path] [options] [expression]

1. Find files by names
  find . -name "file.txt"

2. Find file name by extension
  find . -type f -name "*.pdf"

3. Find Directories by name 
 
 find . -type d -name "project"

4. Case-sensitive name search 

 find . -iname "*.jpg"

5. Find and delete files 
 { Delete all .log files under /tmp}
 
 find /tmp -type f -name "*.log" -delete


{ Finds files larger than 100MB }
6. find . -type f -size +100M

7. Find files modified in last N days

find . -type f -mtime -7

8. Find and execute a command on each File 

find . -type f -name ".sh" -exec chmod +X {} \;
  . Makes all .sh scripts executable 


9. Find empty files or directories

  find . -empty 

10. Find files by permision 

  find . -type f -perm 0777

*************  
Password 

find . -type f -exec file {} \;
🔍 What it does:
. → current directory

-type f → only regular files

-exec file {} → run the file command on each found file

\; → ends the -exec expression (must be escaped

bandit4@bandit:~$ cat ./inhere/-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

