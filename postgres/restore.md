# RESTORE

Restore from dump file.

## Terminal Commands

``` bash
pg_restore -v -C --no-owner --host=localhost --port=5432 --username=postgres --dbname=postgres [DUMP_FILE_NAME].dump
```


Notes
-v: verbose

-C: creates database

--no-owner: ??

--host: location of your local db (usually localhost)

--port: port of your local db (usually 5432)

--username: login for your local admin user (usually postgres)

--dbname: set to postgres to allow restoring when database does not exist yet

