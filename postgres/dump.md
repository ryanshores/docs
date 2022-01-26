# DUMP

Create a dump file for restore.

## Steps

* Create dump file

``` bash
pg_dump --clean -Fc -v --host=[HOST] --username=[USERNAME] --dbname=[DATABASE_NAME] -f [DUMP_FILE_NAME].dump
```

* Drop existing database

``` sql
DROP DATABASE [DATABASE_NAME];
```

### Notes

--clean: this will add drop database to file

-Fc: this specifies custom file format for dump file

-v: verbose

--host: url of sql databse

--username: login

--dbname: name of database to dump

-f: name of dump file

### 