## VPN搭建

VPN是什么？中文翻译叫做：虚拟专用网络。功能是，在公用网络上建立专用网络，进行加密通讯。

#### **适用的场合：**

1. 你的公司网络在一个局域网，不能外部访问。有一天你外出度假了，想访问一下公司的内部网络，外网是不能直接访问的。如果公司的网络有一台主机设置了VPN，你就可以通过连上这台VPN主机，来访问公司内部网络啦。 
2. 如果你的主机是在国外，你可以在这台主机上配置VPN，然后你的电脑连上VPN之后就可以翻墙啦。
3. 某台服务器（如游戏服务器）限制了一些IP连接到它上面，这时你配置VPN，连上VPN之后，就可以继续访问那台服务器咯
4. etc…

#### **服务器情况：**

服务器商：[https://my.vultr.com/](https://my.vultr.com/)

服务器系统：Ubuntu 19.10 x64

#### **搭建步骤：**

mac下Cisco AnyConnect Secure Mobility Client安装包:  
 [http://hacksteven.com/?p=180](http://hacksteven.com/?p=180)  
链接: [https://pan.baidu.com/s/1fKnheWRs5DqVMmWdpIU6pw](https://pan.baidu.com/s/1fKnheWRs5DqVMmWdpIU6pw) 提取码: 2udd 复制这段内容后打开百度网盘手机App，操作更方便哦

IOS手机AnyConnect安装：请到appStore中去搜索下载\(免费\)

参考：[https://tommy.net.cn/2015/02/12/deploy-openconnect-server-with-docker/](https://tommy.net.cn/2015/02/12/deploy-openconnect-server-with-docker/)

安装docker

apt install docker.io

参考：[https://cuiqingcai.com/512.html](https://cuiqingcai.com/512.html)



