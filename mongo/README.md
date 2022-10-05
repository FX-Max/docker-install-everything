# example

## Usage

1. 创建配置，启动容器
```bash
cp .env.example .env
docker-compose up -d mongodb
```

2. 进入容器测试
```bash
docker exec -it mongodb /bin/bash
```

3. 登录 mongo ，执行常用命令，一切 ok
```bash
root@346ac37d2e89:/# mongo admin -u root -p 123456

> show dbs;
admin   0.000GB
config  0.000GB
local   0.000GB
> show collections;
system.users
system.version
> db.version();
5.0.5
```

