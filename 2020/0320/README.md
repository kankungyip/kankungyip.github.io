在使用树莓派的时候，经常希望文件能在局域网内共享，就一定会使用到 Samba 服务器，虽然传输速度不是很快，但是使用简单，服务器配置也很容易，还是比较推荐使用的，下面介绍一下如何安装 Samba 服务器。

## 安装服务器

安装非常简单，只需要一条命令就能解决问题。

```bash
sudo apt-get update
sudo apt-get install samba samba-common-bin
```

!> 如果安装较慢，建议设置国内镜像源，具体参考《[常用工具的国内镜像源](/2019/0712/ "常用工具的国内镜像源")》。

## 配置服务器

因为只是自己使用，我就只使用了最基本的配置，直接共享整个用户目录。配置文件为 `/etc/samba/smb.conf`，这里对它进行修改：

```bash
sudo nano /etc/samba/smb.conf
```

找到并修改下面部分的设置，将用户目录设置共享：

```ini
[home]
comment = Home Directories
browseable = yes
writable = yes
valid users = %S
```

添加树莓派默认的 `pi` 用户，如果默认用户不是 `pi` 就设置成默认用户的名字，这里是访问共享目录所允许的用户：

```bash
sudo smbpasswd -a pi
```

重启 Samba 服务器生效配置：

```bash
sudo samba restart
```
