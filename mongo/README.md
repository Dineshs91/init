### Stop the mongo server in a single command.

`mongo --eval "db.getSiblingDB('admin').shutdownServer()"`
