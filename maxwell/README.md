# example

## Usage

1. 添加配置，启动 mysql 和 redis
```bash
cp .env.example .env
docker-compose up -d maxwell-mysql maxwell-redis
```

2. 查看队列中数据，此时由于还未接入 maxwell，队列为空

```bash
docker exec -it maxwell-redis /bin/bash
root@0720765b7a68:/# redis-cli

127.0.0.1:6379> llen maxwell
(integer) 0
```

3. 新开一个终端，进入 mysql，添加账号分配权限
```bash
docker exec -it  maxwell-mysql /bin/bash
root@6d023f50a4ff:/# mysql -uroot -p123456

mysql> GRANT ALL on maxwell.* to 'maxwell'@'%';
mysql> GRANT SELECT, REPLICATION CLIENT, REPLICATION SLAVE on *.* to 'maxwell'@'%';
mysql> flush privileges;
```

4. 启动 maxwell 
```bash
docker-compose up -d maxwell
```

5. 测试，进入 mysql 容器，插入测试数据
```bash
mysql> create database if not exists `test` default character set utf8;
mysql> use test;
mysql> create table test.test_table(id int not null, name varchar(100));
mysql> insert into test.test_table values(1, 'from master');
mysql> select * from test.test_table;
```

6. 再次进入 redis 容器，查看队列，数据库中的变化已同步到 redis 中
```bash
127.0.0.1:6379> llen maxwell
(integer) 1

127.0.0.1:6379> rpop maxwell
"{\"database\":\"test\",\"table\":\"test_table\",\"type\":\"insert\",\"ts\":1664653000,\"xid\":742,\"commit\":true,\"data\":{\"id\":1,\"name\":\"from master\"}}"
```
