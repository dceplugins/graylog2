# Graylog2

## 介绍

Graylog2 是日志收集服务，支持 TCP 与 UDP 协议，也能够收集 GELF 格式的日志。Docker Compose 配置文件中可以直接定义 syslog 日志输出，将日志发送给 Graylog2 进行收集。

## 安装

通过 DCE 应用仓库部署 Graylog2 应用。

## 使用

编辑需要收集日志的 Compose 配置，加入 logging 字段，在 syslog-address 字段后填写 Graylog2 收集日志的地址，保存并重新部署应用。

```yaml
redis: 
  image: redis
  ports: 
    - "6379"
  logging:
    driver: syslog
    options:
      syslog-address: "tcp://<IP>:<Port>"
```