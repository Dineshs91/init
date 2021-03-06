# Init
A collection of useful linux commands and other stuff.

## ngrep
OS X: `brew install ngrep`

    ngrep -d en1 -q -W byline "GET"
    
## Exclude using `grep`

Exclude matching string using grep. Use `v` argument with grep.

    tail -f access.log | grep -v 'HEAD'

This will exclude all the HEAD requests from `access.log` file.

## Find the pid of a process by name

    pgrep celery
    
## sshconfig

`~/.ssh/config` - Create this file if doesn't exist.

Add the following contents

```
Host dev-machine
    HostName dev.example.com
    Port 22
    User apps
```

You can invoke ssh as `ssh dev-machine`

## Pgrep and kill the process with a single command

`pgrep flower | xargs kill`

## Run a command in background with a single command

`flower -A blog &`

`&` sends the job to background.

You can check the background jobs using `jobs`

## Fuser (Linux)

The fuser command is a very smart unix utility used to find which process is using a file, a directory or a socket. It also gives information about the user owning the process and the type of access. The fuser tool displays the process id(PID) of every process using the specified files or file systems.

`fuser -n tcp 80`

Lists all the processes that are using port 80.

## lsof -i tcp:3000 (OS X)

List the pids of the process listening on port 3000.

`lsof -i tcp:3000`

To only display the pid's use the terse option.

`lsof -t -i tcp:3000`

Also another usage

`lsof -i :3000`

## strace (Linux) or dtruss (OS X)

**strace**
It intercepts and records the system calls which are called
by a process and the signals which are received by a process.  The
name of each system call, its arguments and its return value are
printed on standard error or to the file specified with the -o
option.

`strace -p 1234`

## strace to find out all open system calls

`strace -e open bash`

## List all the files opened by a process

`ls /proc/30880/fd`

where 30880 is the PID.

## /dev/pts (Linux)

```
> tty
/dev/pts/0
```

Switch to another console.

```
echo "Hello World !" > /dev/pts/0
```

The text "Hello World !" would be printed in the first terminal.

## Come out of a broken ssh session.

Press `Enter` `~` `.`

## Compare and generate a diff between 2 directories

`diff -ru dir1/ dir2`

For just the files that have changes

`diff -rqu dir1/ dir2`

## Create a named pipe

`mkfifo my_pipe`

This is similar to shell pipe `|` but uses a file instead.

## Display the env variables of a running process

[Source](http://serverfault.com/a/66366)

`xargs --null --max-args=1 < /proc/self/environ`

## Print the current tty 

The tty command returns the filename of the terminal connected to standard input

`tty`

## Get the PID of the current shell

`echo $$`

## Go back to the previous directory in bash shell

`cd -`

## Change the shell for an user

`usermod -s /bin/bash <username>`

`chsh -s /bin/bash`

## List all the directories with their size

`sudo du -hs *`

## List all the files with their size

`sudo du -h .`

## OS X device block size

`diskutil info / | grep "Block Size"`

## OS X file system block size

`stat -f %k .`

## Get distro info on linux

`cat /etc/issue`

## iotop

Input/Output stats

## Clear bash cmd location hash

The following will clear where bash thinks fab is located:

`hash -d fab`

This command updates the shell's hash of locations of commands
