
https://github.com/kliewkliew/docker-mysql-adventureworks

https://hub.docker.com/r/kliew/mysql-adventureworks

# MySQL-AdventureWorks
MySQL with the Microsoft AdventureWorks sample database converted for MySQL server, from http://sourceforge.net/projects/awmysql/

http://msftdbprodsamples.codeplex.com/
> The AdventureWorks OLTP database supports standard online transaction processing scenarios for a fictitious bicycle manufacturer (Adventure Works Cycles). Scenarios include Manufacturing, Sales, Purchasing, Product Management, Contact Management, and Human Resources.

## Building
`docker build -t kliew/mysql-adventureworks .`

## Running
### Viewing logs
```
docker kill adventureworks
docker rm adventureworks
docker run -it --name adventureworks kliew/mysql-adventureworks
```
or
### In the background
```
docker kill adventureworks
docker rm adventureworks
docker run -d --name adventureworks kliew/mysql-adventureworks
```

### Opening a bash terminal
`docker exec -it adventureworks bash`

### step 1
`docker run -p 3306:3306 -d --name adventureworks -e MYSQL_ROOT_PASSWORD=  kliew/mysql-adventureworks`

### step 2
`mysql`
`use mysql`
`update user set password=password('') where user='sqoop';`
`flush privileges`

### step 3
`ssh root@ip -p 22 -L 3307:localhost:3306`

### step 4
local terminal
`mysql -usqoop -p -h127.0.0.1 -P3307`


