# example

## Usage

1. 添加配置，创建网络
```bash
cp .env.example .env

docker network create apollo
```

2. 启动数据库服务，账号授权
```bash
docker-compose up -d apollo-db

docker exec -it apollo-db /bin/bash

root@4a8959ee8f6c:/# mysql -uroot -p123456

mysql> GRANT ALL PRIVILEGES ON `ApolloPortalDB`.* TO 'apollo'@'%';
```

3. 启动其他服务
```bash
docker-compose up -d apollo-adminservice  apollo-portal apollo-configservice
```

访问：

apollo-portal: [http://127.0.0.1:8070](http://127.0.0.1:8070) 
	默认账号： apollo 默认密码：admin

apollo-configservice: [http://127.0.0.1:8080](http://127.0.0.1:8080)

apollo-adminservice: [http://127.0.0.1:8090](http://127.0.0.1:8090)