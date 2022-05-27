# example

## Usage

```bash
docker-compose up -d redis
```

进入容器测试
```
root@ip-10-0-3-22:/redis# docker exec -it redis /bin/bash
root@8c3303de6c72:/data# redis-cli
127.0.0.1:6379> ping
PONG
```
