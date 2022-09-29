# example

## Usage

```bash
cp .env.example .env

# 修改 docker-compose.yml 文件中的内容，改成你宿主机 IP
KAFKA_ADVERTISED_LISTENERS: PLAINTEXT://192.168.197.121:9092 #宿主机IP

docker network create --gateway 172.28.1.1 --subnet 172.28.0.1/16 net_elk

docker-compose up -d
```

访问： [http://127.0.0.1:5601](http://127.0.0.1:5601)
