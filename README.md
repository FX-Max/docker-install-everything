# docker-install-everything

> install all environments using docker-compose.
> 使用 docker-compose 安装各种服务。

## 特色

- 仅依赖 docker 和 docker-compose，无需本地复杂环境。
- 支持软件和服务多，并且在持续新增。
- 每个文件夹一组(套)服务，根据需要安装即可。
- 所有的文件夹相互独立，无互相依赖，降低使用难度。

## 使用方法

```
git clone https://github.com/FX-Max/docker-install-everything.git
cd docker-install-everything
# 进入里想要安装的服务文件夹后，按照文件夹内的 README 文件介绍使用。
# 以安装 redis 为例：
cd redis
# 根据目录下 README 中的说明操作即可
docker-compose up -d redis
```

## 支持列表

- apollo

    简要说明： Apollo 是一款可靠的分布式配置管理中心，诞生于携程框架研发部，[Apollo](https://github.com/apolloconfig/apollo/)。

- beanstalkd

    简要说明: 高性能，轻量级的分布式内存队列。

- elk

    简要说明: 强大的日志收集和分析解决方案，Elasticsearch + Logstash + Kibana + Filebeat。

- jira

    简要说明: JIRA 是由 Atlassian 公司出品的，被业界公认为最好的项目管理和开发管理工具。

- Maxwell

    简要说明: [Maxwell](https://github.com/zendesk/maxwell)，一个能实时读取MySQL二进制日志Binlog，并生成JSON格式的消息，作为生产者发送给Kafka等系统的应用程序。

- MinIO

    简要说明: 基于 Golang 的一款开源的高性能分布式存储方案，兼容亚马逊S3云存储服务接口。本 docker 版本是单机版本。

- MinIO-cluster

    简要说明: MinIO 分布式集群版本。

- redis

    简要说明: 快速搭建 redis 服务。

- redis-cluster

    简要说明: 快速搭建 redis 集群服务，1主多从多哨兵。

- wikijs

    简要说明： 自建开源的wiki/文档管理系统 wiki.js，[官网](https://js.wiki/)

- wordpress

    简要说明: 快速搭建 wordpress 系统。

- yapi

    简要说明： [YApi](https://github.com/YMFE/yapi) 是一个可本地部署的、打通前后端及QA的、可视化的接口管理平台。

- Yearning

	简要说明： 基于 Go 的开箱即用的MYSQL SQL审核工具。[Yearning](https://github.com/cookieY/Yearning)
