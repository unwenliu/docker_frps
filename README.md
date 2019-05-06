# docker_frps
frp server
## 使用方法
需要搭配docker_frpc使用
### 创建配置文件
在远程服务器里/etc/frps 添加一个frps.ini的配置文件
```ini
[common]
bind_port = 7000
vhost_http_port = 7000
```
### 启动
```bash
docker run -d --restart=always --name frps -v /etc/frps/:/conf -p ${host_port}:${docker_port} unwenliu/frps:latest
```

### 使用docker-compose方式启动
建立docker-compose.yml文件
```yml
version: '3'

services:
  frps:
    image: unwenliu/frps:0.25.0
    network_mode: "host"
    volumes:
      - /etc/frps:/conf
    restart: unless-stopped
```

