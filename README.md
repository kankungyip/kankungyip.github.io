发现一个更好用的个人Blog（文档）框架——[docsify](https://docsify.js.org/ 'docsify')，好用到只需要专心编写文档，
其余一切不管，甚至都不用将markdown文档编译成静态文件，荒废的 Blog 准备重新开始写了。

最近在开发一个少儿编程工具，原本采用Scratch进行二开，后来越做越觉得Scratch框架太过于繁琐，增加一点小功能都很麻烦，
而且限制很多，索性自己从头开发一个新的框架来做。选用了不那么热门的 [Bun.js](https://bun.sh/ 'Bun') 和 
[Preact](https://preactjs.com/ 'Preact') 技术进行开发，由于 [Bun.js](https://bun.sh/ 'Bun') 
实在太新了自己做了一些辅助工具：
[bun-build](https://github.com/kankungyip/bun-build)、
[bun-hot-server](https://github.com/kankungyip/bun-hot-server)、
[bun-index-page](https://github.com/kankungyip/bun-index-page)、
[bun-plugin-copy](https://github.com/kankungyip/bun-plugin-copy)、
[bun-loader-css](https://github.com/kankungyip/bun-loader-css)、
[bun-loader-yaml](https://github.com/kankungyip/bun-loader-yaml)——这些工具还没有发布到NPM。
使用这些工具让开发已经和使用node.js+webpack一样顺手了，重要的是Bun自带的编译打包功能可比webpack快太多了。

![](/2024/0131/blockcode-gui.png 'BlockCode 编程工具')

去年边学边做了几个硬件项目，最新的硬件项目代号 Popsicle——这也是开发上面提到的编程工具的原因之一，
是一个类乐高Spike的编程硬件，具有6个通用接口连接外设，也兼容乐高科技件积木。项目还在开发期，暂时没有更多的图片。

![](/2024/0131/popsicle.png '硬件项目代号 Popsicle')

在开发编程工具的过程中，也萌发了一些新想法，复刻了一个古老的编程游戏——[《坦克大战》](https://make.blockcode.fun/)。
这是一款对坦克进行编程控制实现自主对抗的游戏，和原版的使用代码编程不同，这里采用图形化编程界面，让更多的小朋友可以
在学习图形编程的过程中，多一个练习技术和训练思维的地方。以后将增加联网对战功能，大家就可以把自己编写好的程序分享出去，
和其他玩家编写的程序对抗，不断磨练，更具挑战。现在还只有和电脑AI对战的功能，已经[上线测试](https://make.blockcode.fun/)，
欢迎大家可以体验尝试。

<center>

![](/2024/0131/tankwar.png '《坦克大战》')
![](/2024/0131/tankwar-blocks.png '《坦克大战》编程界面')

</center>

而且[《坦克大战》](https://make.blockcode.com/)这个项目还准备开发配套硬件，作出可以编程的坦克，将虚拟的坦克大战搬到现实中，
在擂台上多个坦克实体对抗，赢取胜利。如果顺利，应该不久就会发布。敬请期待。

以上所有的项目都是自建工作室[BlockCode Lab](https://lab.blockcode.fun/ 'BlockCode Lab')的项目，
也欢迎大家关注我的[BlockCode Lab](https://lab.blockcode.fun/ 'BlockCode Lab')工作室。
