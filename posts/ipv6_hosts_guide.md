# 校园网ipv6-hosts指南
本页简单介绍了在哈工大校园网范围内使用ipv6，以及借助hosts进行科.学.上.网的方法。

*声明：本页旨在交流经验，方便学习生活，请合法使用互联网服务，自行辨别互联网信息，不盲目轻信互联网言论，养成独立思考的习惯。*

[TOC]

### 首先，什么是ipv6？
ipv6简单来说就是“互联网协议版本6”，我们目前广泛使用的是ipv4，关于其详细介绍可以参考百度或者以下链接：[ipv6-用不完的门牌号](http://www.edu.cn/info/ip6/zs/v6/201201/t20120113_731784.shtml)。
### 什么是hosts文件？
目前我们的万维网依赖[DNS](https://baike.baidu.com/item/dns/427444?fr=aladdin)系统来使各主机、终端之间方便的互联，而hosts文件简单来说就是一个将网址域名与对应ip地址建立关联的一个本地文件，详情可以参考[百度百科-hosts](https://baike.baidu.com/item/hosts/10474546?fr=aladdin)。
### 为什么要使用ipv6？
ipv6对于我们普通用户来说，两个简单的用途：**1. 科.学.上.网**，毕竟科研、学习离不开Google，YouTube等视频网站也有很多高质量的视频资源，使用Facebook等社交媒体与国外同学沟通交流；**2. 访问六维等pt站点**，高速下载影视资源(但请自辨版权)，而这些pt站点只能通过ipv6访问; **3. 访问一些ipv6直播站**，可以访问一些ipv6直播服务，观看电视节目......
### 如何使用ipv6？
其实，**中国教育和科研计算机网CERNET**早就接入并支持了ipv6，而窝工又是CERNET的重要节点，所以在窝工校园网范围内是已经支持ipv6的，但使用ipv6还需要路由器、终端设备的支持。

对于PC、笔记本来说，最新的Windows系统、较新的Linux发行版、macOS等都默认支持ipv6协议，而老的WinXP系统可能需要手动安装ipv6协议；而对于移动网络的手机等设备，目前国内三大运营商的4G网络基本都已支持ipv6协议，但一些手机品牌，可能需要前往APN设置，设置开启ipv4/ipv6双协议支持。

而对于路由器来说，目前支持ipv6比较简单的路由器有*极路由*，通过安装教育网ipv6插件(默认配置即可)即可获得ipv6支持，或者购买水星、华硕等路由器，刷openwrt固件获得ipv6的支持。

**而在校内，登录使用**HIT-Wlan**的无线网络，也是支持ipv6协议**的(不过刚登陆后分配地址需要一段时间，稍等一会就好)；另外，**高能物理实验室已支持ipv6**，使用的是Buffalo一款老路由器，有线、无线设备均可获得ipv6支持。

窝工的ipv4/ipv6地址段，可以通过[网络中心主页查询](http://ito.hit.edu.cn/wlgl/list.htm)查询。

此时，Windows用户可以使用命令```ipconfig /all```(Linux、macOS用户```ifconfig```)来查看本机是否获取了ipv6地址；
也可以使用ipv6测试站点来判断是否已经成功接入ipv6网络：[ipv6-test](http://www.test-ipv6.com/)，测试通过如图所示：
![](https://res.cloudinary.com/regulus/image/upload/v1547126528/Github/ipv6-test.jpg)

### 借助ipv6-hosts实现 科.学.上.网
实际上，之前ipv4时代，也可以通过[ipv4的hosts](https://laod.cn/hosts/2018-google-hosts.html)实现科.学.上.网，不过随着GFW升级，解析筛选出来的ipv4-hosts基本都是“见光死”，而因为现有ipv6服务开展还没有那么广泛，GFW对于ipv6-hosts的态度属于“睁一只眼闭一只眼”，所以使用ipv6-hosts相对稳定，并且流量走ipv6通道，在校园网环境中，观看YouTube视频等可以获得很好的网速体验(最好时曾hold住4K视频在线播放)。

#### hosts文件位置
- Windows 系统hosts位于 ```C:\Windows\System32\drivers\etc\hosts```
- Android（安卓）系统hosts位于 ```/etc/hosts```
- Mac（苹果电脑）系统hosts位于 ```/etc/hosts```
- iPhone（iOS）系统hosts位于 ```/etc/hosts```
- Linux系统hosts位于 ```/etc/hosts```
绝大多数Unix系统都是在 ```/etc/hosts```

#### 修改hosts后生效方法
- Windows 开始 -> 运行 -> 输入cmd -> 在命令行窗口输入
```ipconfig /flushdns```

- Linux终端输入
```sudo rcnscd restart```
对于systemd发行版，请使用命令
```sudo systemctl restart NetworkManager```
如果不懂请都尝试下

- Mac OS X终端输入
```sudo killall -HUP mDNSResponder```

*最简单的方式，重启或者注销登录！*

#### ipv6-hosts的获取
1. GitHub:
[lennylxx/ipv6-hosts](https://github.com/lennylxx/ipv6-hosts)
或者直接点击[https://raw.githubusercontent.com/lennylxx/ipv6-hosts/master/hosts](https://raw.githubusercontent.com/lennylxx/ipv6-hosts/master/hosts)，然后将所有内容复制到对应系统的文件内即可，如果对应文件夹没有操作权限，可以将其复制到桌面的一个文本文档内，然后命名为hosts(没有扩展名)，然后拷贝到对应文件夹内即可；
2. laod博客
访问laod博客 [https://laod.cn/hosts/ipv6-hosts.html](https://laod.cn/hosts/ipv6-hosts.html)，直接下载修改好的hosts文件。

#### 可能出现的问题
- 该项目中的ip地址可能包含一些本可以正常访问的地址，诸如：Apple苹果官网，使用该hosts可能使得本可以快速访问的网址访问速度变慢、或者无法访问，如果对其中的一些网址不需要通过ipv6访问，请加```#```注释该行；

- 不同系统因为支持的编码格式以及换行符不同，hosts文件理论上是不能通用的，比如直接从Windows系统拷贝hosts文件到Linux系统中，是不能使用的，但前面提到的复制粘贴、另存新文件是没有问题的。


附：[关于中国的互联网](https://github.com/racaljk/hosts/wiki/%E5%85%B3%E4%BA%8E%E4%B8%AD%E5%9B%BD%E7%9A%84%E4%BA%92%E8%81%94%E7%BD%91)
![](https://res.cloudinary.com/regulus/image/upload/v1547129839/Github/about_CN_Internet.jpg)


20190110


>20190127 UPDATE
截止到2019年1月底，各种渠道获得ipv6的host，已经基本处于不可用状态，不过教育网/科研网内，通过ipv6可以直连Google(YouTube等站点可以打开，但视频不能正常播放)，也许过一段时间会恢复。

>20190221 UPDATE
通过修改DNS等方式还是可以通过ipv6成功访问外站的，说明ipv6可能也没有完全被qiang（如果qiang已建好，DNS污染先行）。修改host的方法可以尝试自lennylxx/ipv6-hosts项目编译而来的新项目[available-ipv6-hosts](https://github.com/huangwenweia/available-ipv6-hosts)，其中由清华DNS解析出的host地址试用比较好(可以访问Google，但YouTube视频难以正常播放)，可以自行尝试。
