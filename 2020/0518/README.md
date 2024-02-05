Xrdp 服务器是一个开源的软件，实现了 Microsoft 远程桌面协议（RDP），可以使用 Microsoft Remote Desktop 以图形化方式远程控制系统。相信大部分人都用过 Remote Desktop 远程桌面软件，树莓派上也可以使用 Remote Desktop 直接远程连接，不需要在客户端上再额外安装软件，Windows 和 macOS 都有很优秀（颜值高）的工具可以直接使用，抛弃 VNC 远程连接树莓派桌面把。

## 安装服务器

安装非常简单，只需要一条命令就能解决问题。

```bash
sudo apt update
sudo apt install xrdp
```

!> 如果安装较慢，建议设置国内镜像源，具体参考《[常用工具的国内镜像源](/2019/0712/ "常用工具的国内镜像源")》。

## 配置服务器

安装好以后，可以运行下列命令来查看是否正确安装并运行：

```bash
systemctl show -p SubState --value xrdp
```

该命令显示 **running** 就表示正确安装并开机运行了。

将运行 Xrdp 服务器的用户添加到 ssl-cert 组：

```bash
sudo adduser xrdp ssl-cert
```

至此 Xrdp 已成功安装，使用 Remote Desktop 客户端连接你的树莓派吧。
