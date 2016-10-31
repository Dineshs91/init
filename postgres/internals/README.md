## Postgres internals

### Display control information of a Postgres sql cluster.

`pg_controldata <data-directory-path>`

### See how data is stored in database specific directories

From psql

`SELECT oid, datname FROM pg_database;`

## References

https://www.packtpub.com/mapt/book/Big+Data+and+Business+Intelligence/9781849516723/2/ch02lvl1sec12/How+PostgreSQL+writes+data
