##### 创建挂载卷

```
mkdir -p /usr/share/elasticsearch/{data,logs}
```

##### 设置权限

```
chmod 777 -R /usr/share/elasticsearch/
```

##### 修改内存配置

```
sysctl -w vm.max_map_count=262144
vi /etc/sysctl.conf
#在尾部添加
vm.max_map_count=262144
```

##### 允许 IPV4 转发

```
vim  /usr/lib/sysctl.d/00-system.conf
#在最下面添加
net.ipv4.ip_forward=1
#重启网络服务
systemctl restart network
```

##### 构建镜像并发布容器

```
docker-compose up --build --force-recreate -d
```
