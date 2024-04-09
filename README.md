$ docker compose exec -it mysql bash

root@8d2b5f03d304:/# mysql -u root -proot fullcycle
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 2
Server version: 5.7.32-log MySQL Community Server (GPL)


mysql> CREATE TABLE categories(id int auto_increment primary key, name varchar(255));
Query OK, 0 rows affected (0.04 sec)


mysql> INSERT INTO categories(name) values('Eletronicos');
Query OK, 1 row affected (0.01 sec)


Configuring mysql connect

http://localhost:9021/clusters
-> Select the existing Cluster 1
-> Menu: Connect
-> Select existing connect-default
-> Add Connector
-> Upload connector config file
  - ./connectors/mysql.properties
  -> Continue
-> Launch

It will be created one topic for each table. As soon as a new data is inserted on the table, it will also be reported to the kafka topic.