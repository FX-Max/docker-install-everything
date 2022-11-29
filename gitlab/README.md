# example

## Usage

```bash
docker-compose up -d gitlab
```

访问： [http://127.0.0.1:80](http://127.0.0.1:80) 

首次登录使用默认的 root 账密登录。
账号为 root 。
密码可以使用如下命令获取：
```
sudo docker exec -it gitlab grep 'Password:' /etc/gitlab/initial_root_password
```
