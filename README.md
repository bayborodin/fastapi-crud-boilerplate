# FastAPI CRUD Boilerplate

A FastAPI based boilerplate. The goal is to build a template that can be used as a starting point for any FastAPI based project.

## Features

- All the goodness of modern, async FastAPI
- Dockerized
- TDD

## Running and testing

```
docker-compose up -d --build
docker-compose exec web pytest .
```

Inspect the database:

```
$ docker-compose exec db psql --username=app --dbname=app_dev
psql (14.4)
Type "help" for help.

app_dev=# \l
                             List of databases
   Name    | Owner | Encoding |  Collate   |   Ctype    | Access privileges
-----------+-------+----------+------------+------------+-------------------
 app_dev   | app   | UTF8     | en_US.utf8 | en_US.utf8 |
 postgres  | app   | UTF8     | en_US.utf8 | en_US.utf8 |
 template0 | app   | UTF8     | en_US.utf8 | en_US.utf8 | =c/app           +
           |       |          |            |            | app=CTc/app
 template1 | app   | UTF8     | en_US.utf8 | en_US.utf8 | =c/app           +
           |       |          |            |            | app=CTc/app
(4 rows)

app_dev=# \c app_dev
You are now connected to database "app_dev" as user "app".
app_dev=# \dt
       List of relations
 Schema | Name  | Type  | Owner
--------+-------+-------+-------
 public | notes | table | app
(1 row)

app_dev=# \q
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
