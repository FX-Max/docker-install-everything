# example

## Usage

```bash
cp .env.example .env
docker-compose up -d minio
```

访问： [http://127.0.0.1:9000](http://127.0.0.1:9000)，使用 .env 中的默认用户`miniouser`，密码`miniopassword`登录。


一般会使用nginx代理访问该服务，下面为对应的 nginx 配置实例。

```
server {
 listen 80;
 server_name minio.example.com;

 ignore_invalid_headers off;
 client_max_body_size 0;
 proxy_buffering off;

 location / {
   proxy_set_header X-Real-IP $remote_addr;
   proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
   proxy_set_header X-Forwarded-Proto $scheme;
   proxy_set_header Host $http_host;

   proxy_connect_timeout 300;
   # Default is HTTP/1, keepalive is only enabled in HTTP/1.1
   proxy_http_version 1.1;
   proxy_set_header Connection "";
   chunked_transfer_encoding off;

   proxy_pass http://localhost:9000;
 }
}
```

参考：[setup-nginx-proxy-with-minio](https://docs.min.io/docs/setup-nginx-proxy-with-minio)
