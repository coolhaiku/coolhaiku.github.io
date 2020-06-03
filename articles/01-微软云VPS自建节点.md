
>有问题总是要解决的，既然别人的东西不好用，那就自己整一个！

## 创建一个虚拟机

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430153956.png#vwid=1367&vhei=313)

>主要是选择 VPS 的大小，这里就以 **美西2** 地区为例，选一个便宜的VPS，型号为 B1s ，价格为 7.59$/月

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430154132.png#vwid=1369&vhei=581)

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200502122049.png#vwid=909&vhei=484)

>磁盘选择免费的64G,否则后期会扣费

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430154307.png#vwid=1366&vhei=591)

>创建完成，可以直接转到控制面板，进行下一步配置

## 简单了解正向代理

这里就放一张以前的图吧，深入的话自己去了解

![](https://i.loli.net/2020/03/08/3OY2kGrV1cjquBz.png#vwid=806&vhei=607)

![代理](https://gitee.com/haikupeng/myblog/raw/master/img/20200329120646.png#vwid=940&vhei=618)

>我们要通过 **本地的电脑** 连接你的美国VPS，接下来直接打开 windows终端 powershell， 输入`ssh 用户名@你的服务器ip地址` ，然后输入密码，就OK了(用户名和密码在前面创建VPS的时候已经填写)

>一台VPS（虚拟专用服务器）能干什么，基本上你的电脑能干什么，他就能干什么，最主要的是它能24小时不断电 不停的跑。不光如此，他还有一个公网IP，任何人都可以通过公网IP访问到这台服务器，你可以简单地理解为IP就是这个服务器的身份证，全球唯一。如果你要把 vps当作代理服务器，他的原理如上图中的正向代理。

## 综合性能测试

打开Xshell或者Putty，输入下列命令：

`wget -qO- bench.sh | bash`

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430125021.png#vwid=618&vhei=405)

实测为一台小弱鸡， I/O 口速度实在是太低了。

- 切换为 root 用户

`sudo -i`

- 开一台机子，要做的第一件事情当然是更新系统啦

`apt update && apt upgrade`

- 安装 Curl

`apt-get update -y && apt-get install curl -y`

## 一键安装 bbr 加速

1. 单命令BBR加速版本

`wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && ./bbr.sh`

2. BBR和BBR puls和魔改BBR和锐速BBR四合一版本：

`wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh`

3. BBR多版本加速集合

`wget -N --no-check-certificate "https://github.com/ylx2016/Linux-NetSpeed/releases/download/sh/tcp.sh" && chmod +x tcp.sh && ./tcp.sh`
 

验证是否安装成功

`uname -r`

输出为版本号则表示 BBR 加速安装完成。

## 安装 V**rAy

>[安装 V**rAy 图文教程]() 以最流行的 **2333333v2** 为例

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430133242.png#vwid=636&vhei=431)

>一直按回车就可以了

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430150459.png#vwid=1366&vhei=590)

>在 vps中输入 `v**rAy` 可以进入控制面板 ，我们把配置连接直接显示出来，输入 `v**rAy url` 即可

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430150808.png#vwid=690&vhei=335)

## Speedtest 测速

>开启全局模式，进入 <https://www.speedtest.net/> 测速

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430150116.png#vwid=1366&vhei=657)

## 更换 VPS 的 ip

>Azure最大的亮点是可以随时无限换IP地址，这当然是极好的，但是正因如此很多IP也是被玩坏了，难免开出被墙IP地址，我们建议通过下面两种方式来更换IP。

（1）直接删除新建虚拟机，这是最直接的办法，就是过程有点繁琐。

（2）在虚拟机控制台操作（有些人制台都找不到，希望不要找我交智商税）

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430132126.png#vwid=996&vhei=480)

>点击控制台的“停止”按钮，会提示你是否保留原来的IP，只要你不勾选，停止后再次启动就是新的IP了！

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430132138.png#vwid=1083&vhei=479)

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200430143421.png#vwid=1091&vhei=417)

>再点击开始，可以重新获取ip

## 转换订阅地址工具

<https://bianyuan.xyz/basic>

## 添加多用户

>在 配置文件中 添加用户id即可，如下图

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200511164337.png#vwid=964&vhei=529)

>clone一个服务器配置文件，修改用户 id 和 alterID

![](https://gitee.com/haikupeng/myblog/raw/master/img/20200511164238.png#vwid=954&vhei=467)

简单的安装及其配置到此结束！后续更新其他配置！
比如套一个域名，伪装传输协议什么的。

## 关于本文

本文只用于学习和测试 VPS 使用，严禁将此用于违法犯罪行为。






