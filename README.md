# pinger
定时检测网络连通性的工具

通过ping探测与目标网络的连通性
在发生故障和故障恢复时通过企业微信群机器人发送通知

### 使用方法
```shell
docker pull jorben/pinger:latest
docker run -d -e DEBUG_MODE=true -e BOTTOM_LINE=75 -e BOT_KEY=请填写你的企业微信机器人KEY -e ADDRESS=www.google.com jorben/pinger:latest
```

### 环境变量说明

- ADDRESS: 探测的目标地址，域名或者IP
- INTERVAL: 探测频率，单位分钟，范围1-60
- BOTTOM_LINE: 连接通过率阈值，低于该阈值触发告警，范围0-100
- ALARM_TITLE: 告警信息标题，默认为"Network Monitor Alarm"
- BOT_KEY: 企业微信群机器人KEY，例如"33b78fe3-16f7-618a-9b95-a38ee312a3f0"，不设置不会触发通知
- DEBUG_MODE: 调试模式 将打印更详细的日志，true或许false