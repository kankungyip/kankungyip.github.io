伟大的天朝大国，使用一些国外的开发工具，总是异常的慢，解决问题的关键就是更换工具的源，替换成国内的镜像源就爽了，收集了一些常用的工具国内源，方便以后使用。

## 国内常用镜像网站

### 大学

1. 清华大学 https://mirrors.tuna.tsinghua.edu.cn
2. 中国科学技术大学 https://mirrors.ustc.edu.cn
3. 浙江大学 https://mirrors.zju.edu.cn
4. 华中科技大学 http://mirrors.hust.edu.cn

### 企业

1. 华为 https://mirrors.huaweicloud.com
2. 腾讯 https://mirrors.cloud.tencent.com
3. 阿里 https://developer.aliyun.com/mirror/
4. 网易 https://mirrors.163.com
5. 淘宝 NPM https://npm.taobao.org/mirrors

## 更换常用开源软件源

### npm

```bash
npm config set registry https://registry.npm.taobao.org
npm config set disturl https://npm.taobao.org/dist
npm config set electron_mirror https://npm.taobao.org/mirrors/electron/
npm config set sass_binary_site https://npm.taobao.org/mirrors/node-sass/
```

### PyPI

```bash
pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U
pip3 config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

### Debian

修改 `/etc/apt/sources.list` 文件内容：

```
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ buster main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ buster main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-updates main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-updates main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-backports main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-backports main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian-security buster/updates main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian-security buster/updates main contrib non-free
```

### Raspbian

修改 `/etc/apt/sources.list` 文件内容：

```
deb http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ buster main non-free contrib rpi
deb-src http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ buster main non-free contrib rpi
```

修改 `/etc/apt/sources.list.d/raspi.list` 文件内容：

```
deb http://mirrors.tuna.tsinghua.edu.cn/raspberrypi/ buster main ui
```
