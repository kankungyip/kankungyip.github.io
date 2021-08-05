
![](/images/codecombat.jpg)

[CodeCombat](https://www.codecombat.com "CodeCombat") 是一款在线的寓教于乐的编程教育产品，最新版本请访问[这里](https://www.codecombat.com "CodeCombat")。CodeCombat 通过循序渐进的游戏过程，让孩子在挑战每一个小关卡的同时不知不觉中掌握编程技能，更培养他们迎难而上的精神和团队协作能力。在线版本经常因为网络问题导致访问速度提不上去，因为是开源软件，可以很方便的搭建离线版，自己在家玩已经足够了。

<!--more-->

在本地架设编程游戏 CodeCombat，按网上的架设教程都无法在本地运行，会直接打开第三方代理的页面。经过仔细的研究，发现官方在早些时候，将原服务器端的代码从开源库主要分支中移除，之后本地运行的版本都通过运行一个代理与官方的服务器通讯，无法再实现完全的本地运行。

通过切换开源库的分支，找到拥有服务器代码的最新分支，再使用老方法就可以实现完全本地运行了，就可以再也不用受限制了。

## 准备工作

所需软件 **Docker**。打开命令行环境。

## 按步就班

{% colorquote info %}
如果你想偷个懒，不想一步一步的来，那就跳过着一节，直接前往[下一节](#一步到位)阅读。
{% endcolorquote %}

新建并运行一个容器。

```bash
$ docker run -it --name $CONTAINER_NAME -p 3000:3000 -w /root debian:stretch /bin/bash 
```

容器运行起来以后，我们下面的步骤都是在容器内操作了。

切换源到阿里的镜像，加速软件包的下载过程。

```bash
$ echo "deb http://mirrors.aliyun.com/debian/ stretch main non-free contrib" > /etc/apt/sources.list
$ echo "deb http://mirrors.aliyun.com/debian-security stretch/updates main" >> /etc/apt/sources.list
$ echo "deb http://mirrors.aliyun.com/debian/ stretch-updates main non-free contrib" >> /etc/apt/sources.list
$ echo "deb http://mirrors.aliyun.com/debian/ stretch-backports main non-free contrib" >> /etc/apt/sources.list
```

安装后续操作所必须要的软件包，如果在后续操作中还提示缺少什么软件包，请自行安装。如果已经安装过这些软件包，请跳过。

```bash
$ apt-get update
$ apt-get install -y --no-install-recommends ca-certificates curl gnupg dirmngr make g++ git python2.7
```

配置你的 Git 信息。

```bash
$ git config --global user.name "$YOUR_NAME"
$ git config --global user.email "$YOUR_EMAIL_ADDRESS"
```

安装 node.js 6，只能是这个版本。

```bash
$ curl -L https://deb.nodesource.com/setup_6.x | bash -
$ apt-get install -y nodejs
$ npm config set registry https://registry.npm.taobao.org
$ npm config set python python2.7
```

安装 MongoDB 2.6，最好是这个 3 以下的版本。

```bash
$ echo "deb http://downloads-distro.mongodb.org/repo/debian-sysvinit dist 10gen" | tee /etc/apt/sources.list.d/mongodb.list
$ apt-get update
$ apt-get install -y --allow-unauthenticated mongodb-org
```

将 MongoDB 先运行起来，后续操作需要导入游戏基础数据库，数据库从官法提供的网址下载，解压后导入到本地数据库中。

```bash
$ service mongod start
$ curl -L http://analytics.codecombat.com:8080/dump.tar.gz | tar xzvf -
$ mongorestore --drop dump
```

> 以上的步骤不能保证未来的任何时候都能正确执行，如果不能执行了，我已将所需文件分享到[阿里云盘](https://www.aliyundrive.com/s/M9FsSDRv8MX "CodeCombat")，请自行下载后解压，再继续执行后面的命令。

获取 CodeCombat 源代码，并切换到最后保留了服务器源代码的分支。

```bash
$ mkdir coco
$ cd coco
$ git init
$ git remote add origin https://github.com/codecombat/codecombat.git
$ git fetch origin production
$ git checkout 2642fd2a97d86bc8c324b2193bf2d4bcb1cf4ee7
```

安装依赖文件，准备运行环境。

```bash
$ npm install node-sass
$ npm install --ignore-scripts
$ npm run bower -- install --allow-root
$ npm install
```

编译前端页面，开启服务器。

```bash
$ npm run webpack
$ npm run nodemon
```

以后再次启动容器只需要以下命令。

```bash
$ docker start $CONTAINER_NAME
$ docker exec -it -w /root/coco $CONTAINER_NAME sh -c "service mongod start && npm run nodemon"
```

## 一步到位

> 如果你觉得以上步骤太过麻烦，也可以通过 Docker 直接导入一个容器然后开始游戏，我已经将容器分享到[阿里云盘](https://www.aliyundrive.com/s/M9FsSDRv8MX "CodeCombat")。

导入准备好的容器镜像文件，创建容器。

```bash
$ docker import coco.tar $IMAGE_NAME
$ docker create -it --name $CONTAINER_NAME -p 3000:3000 -w /root/coco $IMAGE_NAME sh -c "service mongod start && npm run nodemon"
```

启动（停止）容器只需要以下命令。

```bash
$ docker start $CONTAINER_NAME
$ docker stop $CONTAINER_NAME
```

## 开始玩吧

{% colorquote success %}
打开你的浏览器输入地址 localhost:3000，开始开心的玩吧。
{% endcolorquote %}
