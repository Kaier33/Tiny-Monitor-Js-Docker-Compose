
### 说明
> 请确保已经安装了docker 和 docker compose

tiny monitor js的 测试版v0.1版本. 

请确保以下端口没被占用:  
`node` 运行于 `8233`端口  
`redis` 运行于 `2332`端口   
`mysql` 运行于 `2333`端口

#### 测试上报
`curl 127.0.0.1:8233/report-test`

然后进mysql查看是否有新增测试数据.  
mysql端口是:`2333`, 用户:`root`, 密码: `123456`,   
库: `monitor`, 表: `error`

