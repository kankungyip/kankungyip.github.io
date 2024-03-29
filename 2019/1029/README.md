经常在使用 SSH 连接远程服务器时，在一段时间没有向服务器发送命令后链接就断开了，需要关闭再重新连接，很麻烦。有什么办法能一直让连接保持不断开呢？查询网络获得三种主要方法，下面一一来说明。

!> 以下方法均由网络收集得到。

## 服务器

修改服务器的 `etc/ssh/sshd_config`

```
ClientAliveInterval 60 # 服务器每隔60秒发送一次请求给客户端，从而保持连接
ClientAliveCountMax 3 # 服务器发出请求后，客户端没有响应得次数达到 3，就自动断开连接，正常情况下，客户端不会不响应
```

重新启动 SSHD 服务器。

```bash
systemctl reload sshd
```

## 客户端

修改客户端的 `etc/ssh/ssh_config`，添加以下配置项：（在没有权限对服务器配置的情形下）

```
TCPKeepAlive yes # 保持连接
ServerAliveInterval 300 # 客户端每隔300秒发送一次请求给服务器，从而保持连接
ServerAliveCountMax 3  # 客户端发出请求后，服务器端没有响应得次数达到 3，就自动断开连接，正常情况下，服务器不会不响应
```

## 命令行

这样子只会在需要的连接中保持持久连接，毕竟不是所有连接都要保持持久的。

```bash
ssh -o ServerAliveInterval=60 <url>
```
