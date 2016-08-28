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
    
