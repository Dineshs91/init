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

## Fuser

The fuser command is a very smart unix utility used to find which process is using a file, a directory or a socket. It also gives information about the user owning the process and the type of access. The fuser tool displays the process id(PID) of every process using the specified files or file systems.

`fuser -n tcp 80`

Lists all the processes that are using port 80.
