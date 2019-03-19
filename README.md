# docker_frps
frp server
## 使用方法
```bash
docker run -d --restart=always --name frps -v /etc/frps/:/conf -p ${host_port}:${docker_port} unwenliu/frps:latest
```
