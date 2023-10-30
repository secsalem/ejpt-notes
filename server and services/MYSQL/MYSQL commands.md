192.234.100.3
mariadb

show databses;
use database;
show tablename;



|Task|Query|
|---|---|
|List databases|`SHOW DATABASES;`|
|Change active database|`USE dbname;`|
|Change to the “system” database|`USE mysql;`|
|Show tables in active database|`SHOW TABLES;`|
|Show table properties|`DESCRIBE tablename;`|
|List all users|`SELECT user,host,password FROM mysql.user;`|
|List databases|`SELECT host,db,user FROM mysql.db;`|
|Quit|`exit` or `Ctrl-D`|

and more here

https://bertvv.github.io/cheat-sheets/MySQL-MariaDB.html

