## Long running queries


## Number of connections
`db.serverStatus()`

Example:
```json
"connections" : {
	"current" : 37,
	"available" : 782,
	"totalCreated" : 3300979
}
```

## Explain

`query.explain()`

Example:
```
db.users.find({"active": true}).explain()
```

## [Current operation](https://blog.mlab.com/2014/02/mongodb-currentop-killop/)

```
db.currentOp().inprog.forEach(
  function(op) {
    if(op.secs_running > 5) printjson(op);
  }
)
```

## [Current operations waiting for a lock](https://docs.mongodb.com/manual/reference/method/db.currentOp/#write-operations-waiting-for-a-lock)

```
db.currentOp(
   {
     "waitingForLock" : true,
     $or: [
        { "op" : { "$in" : [ "insert", "update", "remove" ] } },
        { "query.findandmodify": { $exists: true } }
    ]
   }
)
```
