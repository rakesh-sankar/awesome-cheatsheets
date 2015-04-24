## change to postgres user and open psql prompt
```bash
sudo -u postgres psql postgres
```

## list databases

```bash
postgres=# \l
```

## list roles

```bash
postgres=# \du
```

## create role

```bash
postgres=# CREATE ROLE demorole1 WITH LOGIN ENCRYPTED PASSWORD 'password1' CREATEDB;
```

## create role with multiple privileges

```bash
postgres=# CREATE ROLE demorole1 WITH LOGIN ENCRYPTED PASSWORD
postgres=# 'password1' CREATEDB CREATEROLE REPLICATION SUPERUSER;
```

## alter role

```bash
postgres=# ALTER ROLE demorole1 CREATEROLE CREATEDB REPLICATION SUPERUSER;
```

## drop role

```bash
postgres=# DROP ROLE demorole1;
```

## create database

```bash
postgres=# CREATE DATABASE demodb1 WITH OWNER demorole1 ENCODING 'UTF8';
```

## grant privileges to new user

```bash
postgres=# GRANT ALL PRIVILEGES ON DATABASE demodb1 TO demorole1;
```

## drop database

```bash
postgres=# DROP DATABASE demodb1;
```

## connect to database

```bash
postgres=# \c <databasename>
```

## list tables in connected database

```bash
postgres=# \dt
```

## list columns on table

```bash
postgres=# \d <tablename>
```

## decribe columns on table

```bash
postgres=# \d+ <tablename>
```

## backup database

```bash
$ pg_dump <databasename> > <outfile> 
```

#### Thanks to [Jason Meridth](http://blog.jasonmeridth.com/posts/postgresql-command-line-cheat-sheet) for creating the list.
