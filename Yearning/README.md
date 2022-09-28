# example

## Usage

```bash
cp .env.example .env
docker-compose up -d
```

> 若发现 mysql 起来了，Yearning 服务未起来。
> docker logs yearning
> 输出：mysql连接失败! 亲 数据库建了没？ 配置填对了没？
> 可以再次执行: docker-compose up -d


访问： [http://127.0.0.1:8000](http://127.0.0.1:8000)
