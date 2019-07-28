## Logging all SQL queries in a spring-boot application using MySQL event handlers

This is an example project for the blog post http://hairoftheyak.com/posts/logging-raw-sql-in-mysql-jdbc-driver

To run:

```
docker-compose up -d
./gradlew bootRun
```

The expected output is something in the style of

```
...
Application      : Saving two new customes
MySQLQueryLogger : SET autocommit=1; /* 1ms */
MySQLQueryLogger : SET sql_mode='STRICT_TRANS_TABLES'; /* 1ms */
MySQLQueryLogger : SET autocommit=0; /* 1ms */
MySQLQueryLogger : insert into customers (name) values ('John Doe'); /* 1ms */
MySQLQueryLogger : insert into customers (name) values ('Jane Doe'); /* 1ms */
MySQLQueryLogger : commit; /* 2ms */
MySQLQueryLogger : SET autocommit=1; /* 0ms */
Application      : Saving done
...
```
