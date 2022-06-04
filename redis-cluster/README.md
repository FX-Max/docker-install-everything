# example

搭建1主3从3哨兵的 redis 集群

## Usage

```bash
cp .env.example .env 
docker-compose up -d
```

- test master

```
docker exec -it redis-server-master redis-cli

127.0.0.1:6379> auth redis
OK
127.0.0.1:6379> ping
PONG
127.0.0.1:6379> info replication
# Replication
role:master
connected_slaves:3
slave0:ip=10.10.10.3,port=6379,state=online,offset=52707,lag=1
slave1:ip=10.10.10.4,port=6379,state=online,offset=52842,lag=1
slave2:ip=10.10.10.2,port=6379,state=online,offset=52842,lag=1
master_failover_state:no-failover
master_replid:11bd4119e3906e4f7c7e1637d100a21bf4c3593c
master_replid2:0000000000000000000000000000000000000000
master_repl_offset:52842
second_repl_offset:-1
repl_backlog_active:1
repl_backlog_size:1048576
repl_backlog_first_byte_offset:1
repl_backlog_histlen:52842
```

- test slave

```
docker exec -it redis-server-slave-1 redis-cli

127.0.0.1:6379> auth redis
OK
127.0.0.1:6379> ping
PONG
127.0.0.1:6379> info replication
# Replication
role:slave
master_host:10.10.10.1
master_port:6379
master_link_status:up
master_last_io_seconds_ago:1
master_sync_in_progress:0
slave_read_repl_offset:145691
slave_repl_offset:145691
slave_priority:100
slave_read_only:1
replica_announced:1
connected_slaves:0
master_failover_state:no-failover
master_replid:11bd4119e3906e4f7c7e1637d100a21bf4c3593c
master_replid2:0000000000000000000000000000000000000000
master_repl_offset:145691
second_repl_offset:-1
repl_backlog_active:1
repl_backlog_size:1048576
repl_backlog_first_byte_offset:1
repl_backlog_histlen:145691
```

- test sentinel

```
docker exec -it redis-server-sentinel-1 /bin/sh
/data # redis-cli -p 26379 -h 10.10.10.5
10.10.10.5:26379> sentinel master mymaster
 1) "name"
 2) "mymaster"
 3) "ip"
 4) "10.10.10.1"
 5) "port"
 6) "6379"
 7) "runid"
```
