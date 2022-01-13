
### 说明
> 请确保已经安装了docker 和 docker compose

tiny monitor js的 测试版v0.1版本. 

请确保以下端口没被占用:  
`node` 运行于 `8233`端口  
`redis` 运行于 `2332`端口   
`mysql` 运行于 `2333`端口

### 开启https


请在 `docker-compose.yml`填入服务器存放域名证书文件夹的绝对路径.   
证书包括 `*.key` 和 ( `*.pem` 或者 `*.crt`)

```
services:
  monit-js-node:
    # build: ./
    image: kaier33/monitjs-node-server:v0.14
    container_name: monit-js-node
    ports:
      - 8233:8233
    volumes:
    # 这里填服务器存放证书的绝对路径 eg: usr/ssl/:/monitjs-node-server/ssl
      - .:/monitjs-node-server/ssl
    depends_on:
      - monit-js-db
      - monit-js-redis

      ...
```

#### 测试上报
`curl 127.0.0.1:8233/report-test`

然后进mysql查看是否有新增测试数据.  
mysql端口是:`2333`, 用户:`root`, 密码: `123456`,   
库: `monitor`, 表: `error`

