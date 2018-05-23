### written with the help of [GitHub Pages] (https://help.github.com/articles/basic-writing-and-formatting-syntax/)

# Unix Notes
 ### List
1. cd - toggles between current & previous working directory
   - cd - : takes us to previous working directory
     - cd $HOME : takes us to home directory
       - cd ~usename : takes us to home directory of given user
         - cd . & cd .. : In Unix, '.' refers to current directory & '..' refers to previous directory
1. pwd
1. PS1 = '$'
2. whoami
3. who
4. ls ( - l, -a, -A , -al, -i)
1. man *command name*
3. clear
1. tty - shows the terminal name
3. who -r - shows current run-level
1. uptime - uptime command shows current time, number of users currently logged on and system load average for past 1, 5 & 15 minutes
2. date - shows date and time
1. date +%D - shows date in DD/MM/YY format
1. date +%d - shows current date (only DD)
1. date +%m - shows current month in digits
1. date +%Y%m%d%H%M%S - shows current date-time in `YYMMDDHHMMSS` format
1. date +%s - shows time in mumber of seconds since Unix was born
1. stat *filename*
1. df -i
1. cat *filename* - display content of file
1. touch - creats or modify timestamp of a file
1. touch -t : To change the timestamp of file.
1. rm - used to remove files. 
   - rm -i : Confirmbefore removing file
   - rm -f : Forcefully removes file
   - rm -r : Recursively remove directory
1. mkdir - used to create a directory
1. rmdir - used to remove directory (if empty)
   - rm -r *filename*
1. ln  - create links for a file
   - ln -s `file1` `file2` : used to create soft link of a file
3. 





### Directory Structure

| Directory | Meaning |
|-----------|---------|
|   /   | The `root Directory` |
|   /bin | Contains Executable Programs |
| sbin | Like/bin, used by system Admins |
|  /usr | Contains Sharable Read only data |
|  /var  | Contain Log Files |
| /home | Home directories for users are in this directory |
| /root | Home directory of root user |
| /etc | Contains Configuration Files |
| /dev | Contains device files |
| /tmp | contains Temperory files |


The `Data Block` contains the actual data of the files and directories.
The `Directory Entry Table` is a table of all files and directories in the directory and their inode numbers.
`Inode Blocks` is where all the are kept.
#### Name of the file is not stored i  inode but it is stored in directory entry of the directory where fileis kept.



| Hard Link | Soft Link |
|-----------|-----------|
| Hard Link is just and another name to the file| Symbolic link.     |
| Same inode and data blocks | different inode number    |
| When we use the rmcommand on a file, one od thebdirectory entries is removed | different file type   |
| A file is said to be removed when number of links reduces to zero | permission may be different  |
| A directory always have atleast two links ("." and actual name od directory) | Number of links will not be increased     |
| Hard Links for directory are not allowed neither can be created using `ln` command. When a directory is created inside a directory,the link count increases by one | size of the file isdifferent   |
| 
