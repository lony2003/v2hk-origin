# v2ray-heroku

## 推荐使用v2hk-refresh, 版本更新，速度更快（可能吧）https://github.com/fangkehou-team/v2hk-refresh
## 如果需要使用VMESS协议（V2ray旧版协议，clash和V2ray均支持该协议而VLESS仅V2ray支持）请暂时使用本项目（另一个不知道出什么问题了。。。。。）

> 部署
# 点击 [![](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/zhangke200377/v2ray-heroku)，[一键部署到heroku](https://heroku.com/deploy?template=https://github.com/xuiv/v2ray-heroku)

客户端config.json设置如下：
```
{
  "log": {
    "loglevel": "warning"
  },
  "inbound": {
    "port": 1080,
    "listen": "127.0.0.1",
    "protocol": "socks",
    "domainOverride": ["tls","http"],
    "settings": {
      "auth": "noauth",
      "udp": true
    }
  },
  "outbound": {
    "protocol": "vmess",
    "settings": {
      "vnext": [{
        "address": "xxxx.herokuapp.com",
        "port": 443,
        "users": [{
          "id": "6625c1aa-29be-4a78-9860-e0e721cd6ff8",
          "alterId": 64
        }]
      }]
    },
    "streamSettings": {
      "network": "ws",
      "security": "tls",
      "tlsSettings": {
        "allowInsecure": true,
        "serverName": null
      }
    },
    "mux": {
      "enabled": true,
      "concurrency": 8
    }
  }
}
```
