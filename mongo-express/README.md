# example

## Usage

```bash
cp .env.example .env
docker-compose up -d mongo
docker-compose up -d mongo-express
```

访问： [http://127.0.0.1:8081](http://127.0.0.1:8081)

账号 dev，密码 dev，见 .env 中 ME_CONFIG_BASICAUTH_USERNAME 和 ME_CONFIG_BASICAUTH_PASSWORD 配置。