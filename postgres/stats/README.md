## List all indexes

```
SELECT i.relname as indname,
       i.relowner as indowner,
       idx.indrelid::regclass,
       am.amname as indam,
       idx.indkey,
       ARRAY(
       SELECT pg_get_indexdef(idx.indexrelid, k + 1, true)
       FROM generate_subscripts(idx.indkey, 1) as k
       ORDER BY k
       ) as indkey_names,
       idx.indexprs IS NOT NULL as indexprs,
       idx.indpred IS NOT NULL as indpred
FROM   pg_index as idx
JOIN   pg_class as i
ON     i.oid = idx.indexrelid
JOIN   pg_am as am
ON     i.relam = am.oid;
```

## Drop index

`DROP INDEX title_idx;`

## Analyze

`ANALYZE`

## Explain analyze

`EXPLAIN ANALYZE select * from users;`

This will display the query plan and the execution time.

## Database config values

`SHOW ALL;`

## View all the live and dead tuples

```sql
SELECT pg_stat_get_live_tuples(c.oid) AS n_live_tup
     , pg_stat_get_dead_tuples(c.oid) AS n_dead_tup
FROM   pg_class c;
```

## Lock monitoring

[Postgres lock monitoring](https://wiki.postgresql.org/wiki/Lock_Monitoring)

## List all locks

```
SELECT * FROM pg_locks;
```
