$ docker compose exec -it mysql bash

root@8d2b5f03d304:/# mysql -uroot fullcycle -proot
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 2
Server version: 5.7.32-log MySQL Community Server (GPL)

mysql> use fullcycle;
Database changed
mysql> CREATE TABLE categories(id int auto_increment primary key, name varchar(255));
Query OK, 0 rows affected (0.04 sec)


mysql> INSERT INTO categories(name) values('Eletronicos');
Query OK, 1 row affected (0.01 sec)