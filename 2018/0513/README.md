上帝第一天，点亮了一盏灯，于是世界有了光明！爱迪生失败多次，点亮了一盏灯，于是黑夜有了光明！micro:bit 正面有 5×5 颗可编程 LED 灯点阵，通过编程来控制这灯点阵，可以玩出很多有意思的东西，如果结合 micro:bit 主板上的其他感应器和控制按钮，甚至可以做出有意思的小游戏。

同学们在学习和了解这些编程原理、控制机制后，充分发挥自己的想象力和创造力，可以做出自己的小小创造和发明。

## LED 亮灯

在 MakeCode 图形编程中，点亮 LED 是一个最基础最简单的过程，将 `显示图标` 或 `显示 LED` 积木块拖放到程序里就可以了，按顺序的排列多个积木块，就可以形成一组动画序列。

### 噗通噗通心跳 :heartpulse:

先来一个简单的图案，我们使用 `显示图标` 积木，选择大心和小心的两个图标，交替显示，形成心跳的动画。

[micro:bit](https://makecode.microbit.org/#pub:_AbTbLA0vqKuL ":include :type=iframe")

### 烟花绽放 :fireworks:

这一次来一个复杂的图案，使用 `显示 LED` 积木，将要显示的图案在 5×5 的点阵中绘制出来，这样就可以点亮对应位置的 LED 灯了。

[micro:bit](https://makecode.microbit.org/#pub:_i4r8pmfHpb0L ":include :type=iframe")

## 按钮控制

通过对 micro:bit 正面的两个可编程按钮（A 和 B）进行编程，实现对程序流程的控制，我们可以制作按钮亮灯的小游戏。

### :smile: 或 :frowning_face:

思路：

1. 启动时，随机显示 :smile: 或 :frowning_face:
2. 按下 A 键，显示显示 :smile:
3. 按下 B 键，显示显示 :frowning_face:

[micro:bit](https://makecode.microbit.org/#pub:_2j44fUivE8g9 ":include :type=iframe")

### 接豆子

MakeCode 里有一个**游戏**的积木块组，这一组积木块可以利用 LED 创建小游戏，将 micro:bit 变成游戏机！

程序逻辑：

1. 启动后，随机从顶端落下豆子（点亮的 LED 灯）
2. 通过 A（左） 和 B（右）控制一个移动的盘子（最底部的一颗 LED 灯）
3. 当盘子成功与落下的豆子接触，就绽放烟花

[micro:bit](https://makecode.microbit.org/#pub:_aezhPwX1CLux ":include :type=iframe")
