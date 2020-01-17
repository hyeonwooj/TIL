# Linux Commands

### alias

The *alias* command lets you give your own name to a command or sequence of commands.

```bash
alias cls=clear
```
This sets up an alias called cls . It will be another name for clear.

### cat

The *cat* command (short for "concatenate") opens the contents of the file to the terminal window. This is faster than opening the file with editor, and it is read only.

```bash
cat .bash_logout
```

if the content is too long use 'less' so you can scroll foward and backword using the arrow key or PgUp and PgDn key. 

```bash
cat .bashrc | less
```

### cd

The *cd* command changes your current directory.

for changing to a directory withon your current directory,
```bash
cd work
```

for changing to a directory elsewhere within the filesystem directory tree,
```bash
cd /user/local/bin
```

for quickly returning to your home directory,
```bash
cd ~
```

for changing to a parent directory,
```bash
cd ..
```

### ls

*ls* lists the file in the current directory.

when you lists files with the -l(long format) option, you will see a string of characters that look like

```bash
ls  -l

-rwxrwxr-x
```

If the first character is '-', it is a file.

If the first character is 'd', it is a directory (folder).

The rest of the string is three sets of three characters.

From the left, the first three represent the file permissions of the *owner*.

The next three represent the file permissions of the *group*.

The rightmost three represent the permissions for *others*.

*r* stands for read, *w* stands for write, and *x* stands for execute. 

If the permission is not granted, *-* appears instead. 

### chmod

The *chmod* command sets the file permissions flags on a file or folder.

One way to use chmod is to provide the permissions you wish to give to the owner, group, and others as a 3 digit number.

The leftmost digit represents the *owner*. The middle digit represents the *group*. The rightmost digit represents the *others*.

The digits you can use and what they represent are listed here:

- 0: No permission
- 1: Execute permission
- 2: Write permission
- 3: Write and execute permissions
- 4: Read permission
- 5: Read and execute permissions
- 6: Read and write permissions
- 7: Read, write and execute permissions

To set the permission to be read, write, and execute (7) for the *owner*, read and write (6) for the *group*, read and execute (5) for the *others*,
```bash
chmod 765 example.txt
```

### chown

The *chown* command allows you to change the owner and group owner of a file.

when you lists files with the -l(long format) option, you will see two names of owners

```bash
ls  -l

-rwxrwxr-x hyeonwooj hyeonwooj 
```
the first indicate the name of the file owner (hyeonwooj)

the second indicate the name of the group owner (hyeonwooj)

You can use chown to change the owner or group, or both of a file. You must provide the name of the owner and the group, separated by a : character. You will need to use sudo. 

To set dave as the owner of the file and mary as the group owner,
```bash
sudo chown dave:mary example.txt
```

### curl

The *curl* command is a tool to retrieve information and files from Uniform Resource Locators (URLs) or internet addresses.

if curl is not provided as a standard part of your Linux distribution, first install curl
```bash
sudo apt-get install curl
```

Suppose you want to retrieve a single file from a GitHub repository. There is no officially supported way to this. You’re forced to clone the entire repository. With curl however, we can retrieve the file we want on its own.
```bash
curl https://raw.githubusercontent.com/torvalds/linux/master/kernel/events/core.c -o core.c
```
*Note that you need to specify the name of the file to save it in, using the -o (output) option. If you do not do this, the contents of the file are scrolled rapidly in the terminal window but not saved to your computer.

### df
The *df* command shows the size, used space, and available space on the mounted filesystems of your computer.

- -h: human readable, displays the sizes in Mb or Gb instead of in bytes.
- -x: exclude, discount filesytem that you are not interest in

```bash
df -h -x squashfs
```
*This shows filesystems except 'squashfs'

### diff

The *diff* command compares two text files and shows the differences between them.

- -y: side by side, shows the difference horizontally
- -w: width, this option let you specify the maximum line width to avoid wraparound lines.  
- --suppress-common-lines: prevents diff from listing the matching lines, letting you focus on the lines which have differences.

```bash
diff -y -W 70 alpha1.txt alpha2.txt --suppress-common-lines
```

### echo

The *echo* command prints (echoes) a string of text to the terminal window.

The command below will print the words “A string of text” on the terminal window.

```bash
echo A string of text
```

The echo command can show the value of environment variables, for example, 
- $USER: hold the values of the name of the user
- $HOME: hold the values of the user’s home directory
- $PATH: hold the values of the name of the path
environment variables. These hold the values of the name of the user, the user’s home directory, andthe path for matching commands when the user types something on the command line.
```bash
echo $USER
```
```bash
echo $HOME
```
```bash
echo $PATH
```

### exit

The *exit* command will close a terminal window, end the execution of a shell script, or log you out of an SSH remote access session.

```bash
exit
```

### find

Use the *find* command to track down files that you know exist if you can’t remember where you put them. You must tell find where to start searching from and what it is looking for. In this example, the . matches the current folder and the -name option tells find to look for files with a name that matches the search pattern.

- '*' represents any sequence of charactoer
- '?' represents any single character

```bash
find . -name *ones*
```
*find any file name containing the sequence “ones”.

restrict the search to files only
```bash
find . -type f -name *ones*
```

for case insensitive search, use iname (insensitive name) option
```bash
find . -iname *wild*
```

### finger

The *finger* command gives you a short dump of information about a user, including the time of the user’s last login, the user’s home directory, and the user account’s full name.


```bash
finger hyeonwooj
```

### free

The *free* command gives you a summary of the memory usage with your computer. It does this for both the main Random Access Memory (RAM) and swap memory. The -h (human) option is used to provide human-friendly numbers and units. Without this option, the figures are presented in bytes.

```bash
free -h
```

### grep

The *grep* utility searches for lines which contain a search pattern.

searching for the word “train” in all text files in the current directory.
```bash
grep train *.txt
```

### groups

The *groups* command tells you which groups a user is a member of.

```bash
groups hyeonwooj
```

### gzip

The *gzip* command compresses files. By default, it removes the original file and leaves you with the compressed version.

- -k: keep, retain both the original and the compressed version

```bash
gzip -k core.c
```

### head

The *head* command gives you a listing of the first 10 lines of a file.

- -n: number, see certain number of lines (default is 10)
```bash
head -n 5 core.c
```

### history

The *history* command lists the commands you have previously issued on the command line. You can repeat any of the commands from your history by typing an exclamation point ! and the number of the command from the history list.
```bash
!188
```

Typing two exclamation points repeats your previous command.
```bash
!!
```

### kill

The *kill* command allows you to terminate a process from the command line. You do this by providing the process ID (PID) of the process to kill.

If PID is 1692, 
```bash
kill 1692
```

### less

The *less* command allows you to view files without opening an editor.

Scroll forward and backward through the file using the Up and Down Arrow keys, the PgUp and PgDn keys and the Home and End keys.

Press Q to quit

```bash
less core.c
```

### man

The *man* command displays the “man pages” for a command in *less*.

to see the man pages for chown
```bash
man chown
```

### mkdir

The *mkdir* command allows you to create new directories in the filesystem. You must provide the name of the new directory to *mkdir*.

to create new directories in the current directory called “invoices",
```bash
mkdir invoices
```

### mv

The *mv* command allows you to move files and directories from directory to directory. It also allows you to rename files.

to move a file called apache.pdf from the “~/Document/Ukulele” directory and placing it in the current directory, represented by the single '.' character.
```bash
mv ~/Documents/Ukulele/Apache.pdf .
```

### passwd

The *passwd* command lets you change the password for a user.

```bash
sudo passwd hyeonwooj
```

### ping

The *ping* command lets you verify that you have network connectivity with another network device. It is commonly used to help troubleshoot networking issues. To use ping, provide the IP address or machine name of the other device.

```bash
ping 192.168.4.18
```
*The ping command will run until you stop it with Ctrl+C.

### ps

The *ps* command lists running processes. Using ps without any options causes it to list the processes running in the current shell.

```bash
ps
```
- -u: user, see all the processes related to a particular user
- -e: every, see every process that is runing
- |less: pipe it through *less*
```bash
ps -e | less
```

### pwd

The *pwd* command prints the working directory (the current directory) from the root / directory.

```bash
pwd
```

### shutdown

The *shutdown* command lets you shut down or reboot your Linux system.

```bash
shutdown
```

### SSH

Use the *ssh* command to make a connection to a remote Linux computer and log into your account.

```bash
ssh hyeonwooj@192.168.0.1
```

### sudo

The *sudo* command is required when performing actions that require root or superuser permissions

```bash
sudo passwd mary
```

### tail

The *tail* command gives you a listing of the last 10 lines of a file.
- -n: number to see certain number of lines, default is 10

```bash
tail -n 5 core.c
```

### tar

With the *tar* command, you can create an archive file (also called a tarball) that can contain many other files. 

- -c: create
- -v: verbose, visual feedback by listing the files to the terminal window as they are added to the archive
- -f: filename
```bash
tar -cvf songs.tar newFolder/
```

### top

The *top* command shows you a real-time display of the data relating to your Linux machine. The top of the screen is a status summary.

```bash
top
```

### uname

You can obtain some system information regarding the Linux computer you’re working on with the *uname* command.

- -a: all, see everything
- -s: kernal name, see the type of kernel
- -r: kernal release, see the kernel release
- -v: kernal version, see the kernel version
```bash
uname -a
```

### w

The *w* command lists the currently logged in users.

```bash
w
```

### whoami

Use *whoami* to find out who you are logged in as or who is logged into an unmanned Linux terminal.

```bash
whoami
```


---
## Refer to
[How-To Geek](https://www.howtogeek.com/412055/37-important-linux-commands-you-should-know/)
