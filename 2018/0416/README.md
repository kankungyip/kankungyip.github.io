![](_media/microbit.jpg)

[micro:bit](https://microbit.org "micro:bit") 是一款由英国广播电视公司（BBC）推出的专为青少年编程教育设计的微型电脑开发板。2016 年 3 月 - 6 月，micro:bit 在英国全线铺开，BBC 在线上线下配套了大量的项目教程资源和活动。BBC 希望通过 micro:bit 驱动青少年参与到创造性的硬件制作和软件编程中去，而不是每天沉浸在各式的娱乐和消费中。

## 初识 micro:bit

### 硬件

![](_media/mb-hardware.png "micro:bit")

### 示例

![](_media/mb-example-1.jpg "电子投篮框")

![](_media/mb-example-2.jpg "继电器电灯")

![](_media/mb-example-3.jpg "3D打印手表")

## micro:bit 编程

micro:bit 的编程软件有很多，支持图形编程、JavaScript、Python 等，我这里主要使用 [MakeCode for micro:bit](https://makecode.microbit.org)，主要原因有三点：

1. 支持图形化、JavaScript 编程环境，入门简单
2. 自带 micro:bit 模拟器，不用真机实时看到代码执行效果
3. 可扩展

其缺点也很明显，只有在线版本（可在 Windows 10 应用商店下载官方离线版），好在这个是开源软件，有很多离线版本可以下载（请自行搜索下载）。

![](_media/makecode-ui.jpg "makecode")

### 第一个程序：:smile: 或 :frowning_face:

思路：

1. 启动时，随机显示 :smile: 或 :frowning_face:
2. 按下 A 键，显示显示 :smile:
3. 按下 B 键，显示显示 :frowning_face:

[micro:bit](https://makecode.microbit.org/#pub:_ezbUeULWufhb ":include :type=iframe")

### 导入 micro:bit

将 micro:bit 连接到电脑上，找到 MICROBIT 盘，点击 MakeCode for micro:bit 编程软件“**下载**”按钮，将 `.hex` 文件保存到 MICROBIT 盘内即可。

![](_media/makecode-download.jpg "下载程序到 micro:bit")
