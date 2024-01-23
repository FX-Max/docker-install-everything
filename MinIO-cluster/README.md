# example

## Usage

> 参考：[https://github.com/minio/minio/blob/master/docs/orchestration/docker-compose/docker-compose.yaml](https://github.com/minio/minio/blob/master/docs/orchestration/docker-compose/docker-compose.yaml)



```bash
cp .env.example .env
docker-compose up -d 
```



**Examples of different disk numbers**

- one disk

```yaml
services:
  minio1:
    <<: *minio-common
    hostname: minio1
    volumes:
      - /mnt/disk1/minio1/data1:/data1
      - /mnt/disk1/minio1/data2:/data2

  minio2:
    <<: *minio-common
    hostname: minio2
    volumes:
      - /mnt/disk1/minio2/data1:/data1
      - /mnt/disk1/minio2/data2:/data2

  minio3:
    <<: *minio-common
    hostname: minio3
    volumes:
      - /mnt/disk1/minio3/data1:/data1
      - /mnt/disk1/minio3/data2:/data2

  minio4:
    <<: *minio-common
    hostname: minio4
    volumes:
      - /mnt/disk1/minio4/data1:/data1
      - /mnt/disk1/minio4/data2:/data2
```



- two disks

```yaml
services:
  minio1:
    <<: *minio-common
    hostname: minio1
    volumes:
      - /mnt/disk1/part1:/data1
      - /mnt/disk2/part1:/data2

  minio2:
    <<: *minio-common
    hostname: minio2
    volumes:
      - /mnt/disk1/part2:/data1
      - /mnt/disk2/part2:/data2

  minio3:
    <<: *minio-common
    hostname: minio3
    volumes:
      - /mnt/disk1/part3:/data1
      - /mnt/disk2/part3:/data2

  minio4:
    <<: *minio-common
    hostname: minio4
    volumes:
      - /mnt/disk1/part4:/data1
      - /mnt/disk2/part4:/data2
```



- four disks

```yaml
services:
  minio1:
    <<: *minio-common
    hostname: minio1
    volumes:
      - /mnt/disk1/part1:/data1
      - /mnt/disk2/part1:/data2

  minio2:
    <<: *minio-common
    hostname: minio2
    volumes:
      - /mnt/disk1/part2:/data1
      - /mnt/disk2/part2:/data2

  minio3:
    <<: *minio-common
    hostname: minio3
    volumes:
      - /mnt/disk3/part1:/data1
      - /mnt/disk4/part1:/data2

  minio4:
    <<: *minio-common
    hostname: minio4
    volumes:
      - /mnt/disk3/part2:/data1
      - /mnt/disk4/part2:/data2
```



- eight disks

```yaml
services:
  minio1:
    <<: *minio-common
    hostname: minio1
    volumes:
      - /mnt/disk1:/data1
      - /mnt/disk2:/data2

  minio2:
    <<: *minio-common
    hostname: minio2
    volumes:
      - /mnt/disk3:/data1
      - /mnt/disk4:/data2

  minio3:
    <<: *minio-common
    hostname: minio3
    volumes:
      - /mnt/disk5:/data1
      - /mnt/disk6:/data2

  minio4:
    <<: *minio-common
    hostname: minio4
    volumes:
      - /mnt/disk7:/data1
      - /mnt/disk8:/data2
```



