##### 创建挂载卷

```
mkdir -p /usr/share/elasticsearch/{data,logs}
```

##### 设置权限

```
chmod 777 -R /usr/share/elasticsearch/
```

##### 构建镜像并发布容器

```
docker-compose up --build -d
```
