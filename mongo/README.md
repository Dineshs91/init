### Stop the mongo server in a single command.

`mongo --eval "db.getSiblingDB('admin').shutdownServer()"`

### Performance monitoring

`mongostat --username root --password password --authenticationDatabase admin`

`mongotop --username root --password password --authenticationDatabase admin`
