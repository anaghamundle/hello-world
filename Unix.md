> ### written with the help of [GitHub Pages](https://help.github.com/articles/basic-writing-and-formatting-syntax/)

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
1. touch - creates or modify timestamp of a file
1. touch -t : To change the timestamp of file.
1. rm - used to remove files. 
   - rm -i : Confirm before removing file
   - rm -f : Forcefully removes file
   - rm -r : Recursively remove directory
1. mkdir - used to create a directory
1. rmdir - used to remove directory (if empty)
   - rm -r *filename*
1. ln  - create links for a file
   - ln -s `file1` `file2` : used to create soft link of a file
3. cp - copies file or files to the destination.
   - cp -r : -r option is required while copying a directory and its content.
1. mv - move or rename files & directories
1. vi *filename* - Used to open file in vi Editor.
1.





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

`Inode Blocks` is where all the inodes are kept.
#### Name of the file is not stored in the inode but it is stored in directory entry of the directory where file is kept.



| Hard Link | Soft Link |
|-----------|-----------|
| Hard Link is just and another name to the file| Symbolic link.     |
| Same inode and data blocks | different inode number    |
| When we use the rmcommand on a file, one od thebdirectory entries is removed | different file type   |
| A file is said to be removed when number of links reduces to zero | permission may be different  |
| A directory always have atleast two links ("." and actual name od directory) | Number of links will not be increased     |
| Hard Links for directory are not allowed neither can be created using `ln` command. When a directory is created inside a directory,the link count increases by one | size of the file is different   |

The *vi* editor is the default editor in Unix. It has two main modes of operation, the `Command Mode` & `Insert Mode`.
Insert mode is used to enter text whereas to navigate or copy/paste we have to use the command mode.

| Keys | Comments |
|------|----------|
| i/a | Insert or append mode |
| I/A | go to start/end of line and then change to insert mode |
| h/j/k/l | cursor left/down/up/right |
| w/b | word backward/forward |
| x/dd | delete character/line |
| yy | copy line |
| p | paste |
| :%s/foo/bar/g | Changes all occurances of foo with bar |
| :wq | Save and quit |
| :w new.txt | Save as new.txt |
| :q! | Quit but dont save |
| more | To see the file content a screen at a time |
| less | To see the file one page at a time |
| g/G | Start/end of the file |

the **find** is used to find files in directories. By default, find is recursive. 

*Filters*
1. cat
1. head
1. tail
1. cut
1. sort
1. tr
1. grep


| sort | sort alphabeically by default |
|-------|-------------------------------|
| -t	| used as delimiter |
| -k	| used as column |
| -r | sort in reverse order |

| tr | Translate characters |
|----|----------------------|
| -s | squeeze consecutive occurences of character |
| -d | delete all occurences of given character |

| cut | cut vertically |
|-----|----------------|
|  -d | The default delimiter is TAB which can be changed with switch -d |			
| -f | Reperesents the field (like column) |

| wc | Count and print line, words and bytes count |
|-----|--------------------------------------------|
| -l | shows lines |
| -w | shows word count |


| grep | Searches for pattern and prints the entire line containing the pattern |	
|------|------------------------------------------------------------------------|
| -- color | displays matched pattern in color |
| -e | specify multiple search patterns |
| -f | provide file as pattern |
| -i | ignore case |
| -v (vagal) | show all lines which have not been matched with given pattern |
| -w | matches pattern if it is a whole word |
| -x | matches pattern if it is a whole line |
| -c | print count of the matching pattern |
| -l | shows file name where pattern has matched |
| -L | shows file name where pattern has not matched |
| -m NUM | stop reading file after Num matching lines |
| -o | print pattern only |
| -q | [quiet] suppress output and only written exit code |


| cat | Concatenate files and print on standard output |
|-----|------------------------------------------------|
| -n | number all lines |
| -e | shows $ at the end of each line |
| -s | Suppress repeated empty output lines |
| -v | shows non printable character except line ending character and TAB|
| -T | Displays TAB as ^ |


| head	- number | Show first part of files |
|---------------|--------------------------|
| tail	- number | Show last part of files |
| -n +number | Show last part of files starting with given number |

ifcongig -a
*sudo -i* : sudo lets you run commands in your own user account with root privileges. *su* lets you switch user so that you're actually logged in as root. After running sudo -i all subsequent commands you run will be run as though you had run them with sudo.
sudo -s runs a shell with root privileges.
*adduser* : To create user
*groupadd* : Create a new group
*groupdel* : delete a group 
*id* : command shows UserID and GroupID
*/etc/passwd* : When user account created or deleted, this file gets updated automatically. Each line in this file represents user account information. Username:x(encrypted password file):UserID:GruoupID:Description of the user(e.g.full name/work phone):User home directory:User's default shell
/etc/group: shows list of groups.
*/etc/skel* : It isa directory which contains files and directories that are automatically copied to new user's home directory when user is created using *adduser*. It allows Admin to create default home directory for all users. 
