# example

## Usage

1. 添加配置。
```bash
cp .env.example .env
```

2. 根据实际情况修改 .env 中的配置，主要是 DB_HOST 和 REDIS_HOST 改成自己的 MySQL 和 Redis 服务地址。

3. 连接到 MySQL ，根据 .env 文件中的配置，创建数据库账号和分配权限。
```bash
create database jumpserver default charset 'utf8';
create user 'jumpserver'@'%' identified by 'nu4x599Wq7u0Bn8EABh3J91G';
grant all on jumpserver.* to 'jumpserver'@'%';
flush privileges;
```

4. 启动 core 服务。

```bash
docker-compose up -d core
```

5. 启动其余服务。
```bash
docker-compose up -d
```

6. 访问后台界面。
访问： [http://127.0.0.1:80](http://127.0.0.1:80)
初始账号： admin
初始密码： admin


