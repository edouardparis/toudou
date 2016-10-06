# Toudou: a mini tasks manager api

## Set up your api

1. Create PostgreSQL Database:
  * install Postgre and sqlit3 for the tests
  * create database and user
  * import database set up with  `toudou=# \i database.sql; `

2. Get dependencies and compile

```
go get github.com/gin-gonic/gin
go get github.com/jinzhu/gorm
go get github.com/lib/pq
go get github.com/mattn/go-sqlite3
go get github.com/stretchr/testify/assert

```
```
go install

```

## Make it work

```
DATABASE_USER=username DATABASE_NAME=dbname DATABASE_PASSWORD=dbpassword toudou

```

## Test your api


```
curl -i -X POST -H "Content-Type:application/json" -d "{ \"name\": \"third task\", \"description\":\"find some coffee\"}" http://localhost:8080/tasks

```

```
curl -i -X PATCH -H "Content-Type:application/json" -d "{ \"name\": \"task 1 updated\", \"description\":\"pants are optionnal\"}" http://localhost:8080/tasks/1

```

test task package

```
cd task
go test
```

## What else ?

All your tasks are returned in ascendant creation date order.
