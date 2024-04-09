# Full Cycle - Kafka Connect

Based on the course: "Full Cycle 3.0 - Kafka"


## Web Interface

Kafka control-center
http://localhost:9021/

Mongodb
http://localhost:8085/
admin
pass

## Reference

Kafka Connectors:
https://www.confluent.io/hub/ 

Single Message transformation:
https://docs.confluent.io/platform/current/connect/transforms/overview.html

## Setup

### Setup mysql database

Connecting to mysql docker and database
```
$ docker compose exec -it mysql bash


root@8d2b5f03d304:/# mysql -u root -proot fullcycle
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 2
Server version: 5.7.32-log MySQL Community Server (GPL)
```

Creating database
```
mysql> CREATE TABLE categories(id int auto_increment primary key, name varchar(255));
Query OK, 0 rows affected (0.04 sec)


mysql> INSERT INTO categories(name) values('Eletronicos');
Query OK, 1 row affected (0.01 sec)
```

### Setup Kafka connect

#### Setup mysql connect

http://localhost:9021/clusters
- Select the existing Cluster 1
- Menu: Connect
- Select existing connect-default
- Add Connector
- Upload connector config file: `./connectors/mysql.properties`
- Click on Continue button
- Click on Launch button

It will be created one topic for each table. As soon as a new data is inserted on the table, it will also be reported to the kafka topic.

#### Setup mongodb sinc

Follow the same steps as before, however, uploading the following file:

./connectors/mongodb.properties