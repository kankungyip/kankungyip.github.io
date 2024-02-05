![](_media/big-sur.jpg)

macOS Big Sur 是 Apple 公司最新的操作系统，大家都可以通过 MAS 在线升级到最新版本。但是对于网络较慢或者有一些特殊要求的用户来说，最好能使用 U 盘离线安装，这里就来说一下使用命令行制作独立的 USB 安装盘。

## 安装步骤

1. 在 [MAS](https://apps.apple.com/cn/app/macos-big-sur/id1526878132?mt=12) 下载 macOS Big Sur 正式版安装程序，下载完后直接退出安装程序。

2. 格式化一个至少 16GB 的 U 盘，使用“macOS”名字，“Mac OS 扩展（日志式）”格式，“GUID 分区图”方案。

3. 打开 “应用程序 → 实用工具 → 终端”，将下面的一段命令复制并粘贴进去：

   ```bash
   sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/macOS --nointeraction
   ```

   执行上面这段命令期间会需要输入电脑密码和回车，然后等待，等待屏幕最后出现 **Done**，就大功告成了。

4. 重启电脑，并且在启动的时候按住“Option”键，待屏幕出现选择启动盘时，你知道怎么做了！

!> 使用 Apple M1 芯片的电脑，开机时需要按住电源键不松，直到出现启动选项。
