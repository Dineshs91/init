## AWK commands

Prepend all the lines in a file with export. (To be sourced `source .env.test`)

`awk '$0="export "$0' .env.example > .env.test`
