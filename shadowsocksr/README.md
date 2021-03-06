# 安装
先配置好软件源  
```bash
sudo apt update  
sudo apt upgrade  
wget -N --no-check-certificate https://raw.githubusercontent.com/xu9010/shadowsocks_install/master/shadowsocksR.sh && bash shadowsocksR.sh
```
（Fork自https://github.com/91yun/shadowsocks_install）

# 一些必要的信息
配置文件路径：/etc/shadowsocks.json  
日志文件路径：/var/log/shadowsocks.log  
安装路径：/usr/local/shadowsocks/shadowsoks  

启动：/etc/init.d/shadowsocks start  
停止：/etc/init.d/shadowsocks stop  
重启：/etc/init.d/shadowsocks restart  
状态：/etc/init.d/shadowsocks status  

# 参考配置文件
## 开启SSR（兼容SS）
```json
{
    "server":"0.0.0.0",
    "server_ipv6":"::",
    "server_port":12345,
    "local_address":"127.0.0.1",
    "local_port":1080,
    "password":"YOUR_PASSWORD",
    "timeout":120,
    "method":"aes-256-cfb",
    "protocol":"auth_sha1_v4_compatible",
    "protocol_param":"",
    "obfs":"http_simple_compatible",
    "obfs_param":"",
    "redirect":"",
    "dns_ipv6":false,
    "fast_open":false,
    "workers":1
}
```

## 开启SSR（兼容SS）多端口
```json
{
    "server":"0.0.0.0",
    "server_ipv6":"::",
    "local_address":"127.0.0.1",
    "local_port":1080,
    "port_password":{
        "12345":"YOUR_PASSWORD1",
        "12346":"YOUR_PASSWORD2"
    },
    "timeout":120,
    "method":"aes-256-cfb",
    "protocol":"auth_sha1_v4_compatible",
    "protocol_param":"",
    "obfs":"http_simple_compatible",
    "obfs_param":"",
    "redirect":"",
    "dns_ipv6":false,
    "fast_open":false,
    "workers":1
}
```
# 参考
https://www.91yun.org/archives/2079  
ShadowsocksR 协议插件文档 https://github.com/breakwa11/shadowsocks-rss/blob/master/ssr.md

