# example

## Usage

启动容器
```bash
docker-compose up -d jenkins
```

查看容器日志
```bash
docker logs -f jenkins
```

访问： [http://127.0.0.1:8080](http://127.0.0.1:8080)
初次启动时，可能需要等待2-3分钟，jenkins 服务才会启动完成。

jenkins 启动好之后，按照要求输入管理员密码，内容在 `/var/jenkins_home/secrets/initialAdminPassword` 中，对应是本地当前文件夹下 `data/jenkins_home/secrets/initialAdminPassword`。

