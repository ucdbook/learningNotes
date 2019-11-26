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

mac下Cisco AnyConnect Secure Mobility Client安装包: [http://hacksteven.com/?p=180](http://hacksteven.com/?p=180)

IOS手机AnyConnect安装：请到appStore中去搜索下载\(免费\)

参考：[https://tommy.net.cn/2015/02/12/deploy-openconnect-server-with-docker/](https://tommy.net.cn/2015/02/12/deploy-openconnect-server-with-docker/)

安装docker

apt install docker.io

参考：[https://cuiqingcai.com/512.html](https://cuiqingcai.com/512.html)

我们以Ubuntu为例，说一下怎样配置VPN服务器。

1、用root账户登陆服务器

2、安装PPTPD

3、编辑pptpd.conf文件

| 1 | vi/etc/pptpd.conf |
| :--- | :--- |


取消注释下面内容

| 12 | localip192.168.0.1remoteip192.168.0.234-238,192.168.0.245 |
| :--- | :--- |


这几句的意思是：当外部计算机通过pptp联接到vpn后所能拿到的ip地址范围和服务器的ip地址设置。

4、添加用于登陆的账户

| 1 | vi/etc/ppp/chap-secrets |
| :--- | :--- |


格式如下：

| 12 | \# client server secret IP addressescqcpptpd123456\* |
| :--- | :--- |


从左到右依次是用户名，自己指定。服务器，填写pptpd，密码，自己指定。IP，填\*即可。中间用空格分别隔开。

5、设置DNS解析，编辑pptpd-options文件

| 1 | vi/etc/ppp/pptpd-options |
| :--- | :--- |


找到ms-dns，取消掉注释，并修改DNS地址，这里我推荐大家用

Google DNS 8.8.8.8 和 8.8.4.4

更改为如下内容

| 12 | ms-dns8.8.8.8ms-dns8.8.4.4 |
| :--- | :--- |


6、开启转发

| 1 | vi/etc/sysctl.conf |
| :--- | :--- |


取消注释以下内容

| 1 | net.ipv4.ip\_forward=1 |
| :--- | :--- |


这句话意思是：打开内核IP转发

更新一下配置

| 1 | sudosysctl-p |
| :--- | :--- |


7、安装iptables并设置

| 12 | apt-getinstalliptablessudoiptables-tnat-APOSTROUTING-s192.168.0.0/24-oeth0-jMASQUERADE |
| :--- | :--- |


后面这句话作用是：立刻让LINUX支持NAT\(platinum\)

8、重新启动服务

| 1 | /etc/init.d/pptpdrestart |
| :--- | :--- |


9、大功告成，VPN服务器就这么配置好啦。

接下来，利用IP地址，刚才设置的VPN账号和密码，就可以连你的VPN啦。

