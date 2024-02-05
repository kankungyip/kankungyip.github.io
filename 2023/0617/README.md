![](_media/PicoArcade.jpeg "PicoArcade")

近期在学习做硬件，恶补了好多硬件工程的知识，在[嘉立创 EDA](https://lceda.cn/)画了一块基于树莓派 Pico 的游戏扩展板，带有 240×240 的 16 位色屏幕、9 个可编程按键——其中 8 个按键使用导电硅胶按键，匹配 Switch Lite 的按键、一个蜂鸣器、还有一个 6P 的扩展口（干嘛用还没想好），电源采用 3.7V 锂电池，通过 USB-C 进行充电和下载游戏。

因为是基于树莓派 Pico 做的，所以直接使用 MicroPython 就可以进行编程，没有单独设计开发游戏的 SDK，等以后有空了再补全这个，也可以更方便的开发游戏，或许还会做一个图形化的编程工具，就齐活了。

做了一个简单的贪吃蛇的游戏 Demo，运行还是很流畅的，树莓派 Pico 是非常不错的一个小开发板。

[youku](https://player.youku.com/embed/XNjM2NzQxNjA0NA== ":include :type=iframe allowfullscreen height=498")

!> 看别人在树莓派 Pico 上做了 FC 模拟器，应该可以移植一个下载到我的 PicoArcade 里玩，等有空吧！:laughing:

该硬件项目在[立创开源硬件平台](https://oshwhub.com/kankungyip/picoarcade "PicoArcade")已经开源。

![](//image.lceda.cn/histories/3e615382a97d42b5865af40e54639867.png)

![](//image.lceda.cn/histories/352fd179f9e94bf5bc31db0dcc1e7199.png)
