![](cb1.png)

CB1 核心板是 [BIGTREETECH](www.bigtree-tech.com) 推出的一款兼容树莓派 CM4 的平替板，与 CM4 拥有相同的 BTB 座子，可以兼容市面上的大部分 CM4 的 IO 板，只是不能使用 CSI 和 DSI 接口。

CB1 核心板使用的是全志 H616，拥有四核 ARM Cortex-A53@1.5GHz，支持 OpenGL3.2，1GB 的内存，可以使用 HDMI2.0A 输出，支持 4K 显示器，100M 以太网和 WiFI，可以高效的运行 Linux 系统。

在系统方面，CB1 核心板采用定制的 Debian，可以在 BigTree-Tech 的 GitHub [下载](https://github.com/bigtreetech/CB1/releases) 最新系统，默认下载的最小系统是不含桌面系统的，为了方便学习，自然需要安装一个精简的图形桌面，经过对比，选择了安装 [Xfce4](https://xfce.org)。

## 安装前准备

### 升级系统

```bash
apt update
apt upgrade
```

### 安装 Xorg 服务

```bash
apt install xorg
```

## 安装 Xfce4

```bash
apt install xfce4 xfce4-goodies
```

### 关于 `xfce4-goodies`

`xfce4-goodies` 包含了很多使用的软件，推荐安装，也可以选择部分软件安装，可以参考下表：

| 包 | 说明 |
| --- | --- |
| xfce4-artwork | Xfce 桌面环境美化的扩展包、会安装一些图标、主题、壁纸 |
| xfce4-battery-plugin | 电池电量的显示器 |
| xfce4-clipman-plugin | 剪切板历史记录查看 |
| xfce4-cpufreq-plugin | 设置CPU频率 |
| xfce4-cpugraph-plugin | CPU利用率查看 |
| xfce4-datetime-plugin | 日期和时间插件 |
| xfce4-diskperf-plugin | 磁盘情况监控 |
| xfce4-fsguard-plugin | 文件系统监控 |
| xfce4-genmon-plugin | 显示一些命令提示 |
| xfce4-mailwatch-plugin | 邮件通知 |
| xfce4-mount-plugin | 挂载管理 |
| xfce4-netload-plugin | 网络 |
| xfce4-notes-plugin | 笔记 |
| xfce4-places-plugin | 快速管理收藏夹、最近使用、可移除驱动器 |
| xfce4-quicklaunchers | 快速启动 |
| xfce4-sensors-plugin | 传感器、可以查看硬件温度 |
| xfce4-smartbookmark-plugin | 收藏夹 |
| xfce4-systemload-plugin | 系统加载项查看 |
| xfce4-timer-plugin | 计时器 |
| xfce4-verve-plugin | 提供命令记忆功能 |
| xfce4-wavelan-plugin | 无线网运行情况 |
| xfce4-weather-plugin | 天气预报 |
| xfce4-xkb-plugin | 键盘配置 |
| thunar-archive-plugin | 压缩文件的解压插件 |
| thunar-media-tags-plugin | 提供媒体文件标签功能 |
| mousepad | 一个简单的文本编辑器 |
| ristretto | 图像查看器 |
| xfburn | DVD 刻录软件 |
| xfce4-dict | 词典 |
| xfce4-notifyd | 通知 |
| xfce4-screenshooter | 截图 |
| xfce4-taskmanager | 任务管理器 |
| xfce4-terminal | 终端 |
| xfce4-cellmodem-plugin | 调制解调器 |
| xfce4-linelight-plugin | 一个搜索程序 |
| xfce4-messenger-plugin | DBus消息通知 |
| xfce4-minicmd-plugin | 额外的终端软件 |
| xfce4-mpc-plugin, xfmpc | Music Player Daemon 播放器守护程序，管理播放列表和音乐数据库 |
| xfce4-radio-plugin | 收音机插件 |
| xfce4-xfapplet-plugin | 提供GNOME环境中的一些小应用程序支持 |
| xfswitch-plugin | 用户快速切换 |
| xfce4-hdaps | ThinkPads 的 HDAPS 插件 |
| thunar-thumbnailers | 为文件管理器提供图像预览功能 |
| gigolo | GIO/GVfs 虚拟文件系统的远程管理前端 |
| parole | 视频播放器 |
xfce4-power-manager: 电源管理

### 安装 LightDM

```bash
apt install lightdm lightdm-gtk-greeter
```

#### 设置开机自动运行 LightDM

```bash
systemctl enable lightdm
```

## 设置中文

### 安装中文字体

```bash
apt install fonts-wqy-zenhei fonts-wqy-microhei
```

### 设置语言编码

```bash
apt install locales
dpkg-reconfigure locales
```

#### 选择下面语言编码

1. en_US.UTF-8
2. zh_CN.GB2312
3. zh_CN.GBK
4. zh_CN.UTF-8
5. zh_TW.BIG5
6. zh_TW.UTF-8

默认语言编码选择：zh_CN.UTF-8

### 查看并设置默认语言

```bash
nano /etc/default/locale
```

打开文件后，将内容改为：

```ini
LC_MESSAGES=zh_CN.UTF-8
LANG=zh_CN.UTF-8
LANGUAGE=zh_CN.UTF-8
```
