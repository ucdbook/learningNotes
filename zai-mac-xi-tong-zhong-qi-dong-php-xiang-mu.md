**apache**

启动apache服务：（Mac系统自带apache服务器）

第一步：启动apache服务：在终端下输入命令 sudo apapchectl start

第二步：查看apache服务版本：sudo apachectl -v

![](https://img2018.cnblogs.com/blog/1177379/201906/1177379-20190613150148337-279061826.png)

第三步：在浏览器输入网址[http://localhost或者](http://localhost或者) [http://127.0.0.1查看服务器是否连接成功](http://127.0.0.1查看服务器是否连接成功)

```
        若成功：显示It works！
```

其他apache配置：

关闭apache服务：sudo apachectl stop

重启apache服务：sudo apachectl restart

apache服务安装路径：etc/apache2\(属于私有目录 在finder上直接看不到，可以在终端上输入cd / 回车 后输入cd etc/apache2可以查看\)

apache服务部署路径：Library/Webserver/Documents（我们的项目需要放在该路径下）

注1: 笔者使用Sublime Text软件进行PHP开发,且该软件可以直接打开该配置文件

```
                                   注2: 如果提示文本锁定不允许修改,可以将该文件复制到其他文件夹修改之后,在粘贴回来覆盖原文件即可
```

**PHP**

PHP启动只需要在apache服务中做一些配置就可以启动

输入命令进入etc/apache2中

找到httpd.conf文件，输入命令sudo vim httpd.conf进入编辑

搜索找到\#LoadModule php5\_module libexec/apache2/libphp5.so 讲前面的‘\#’删除

重启apache服务器即可：sudo apachectl restart

测试：在Library/Webserver/Documents目录下建立一个test.php文件进行测试

```
    后在浏览器中输入：http://localhost/test.php可以看到你写的内容
```

**mysql**

安装MySQL：

在浏览器中输入网址`http://dev.mysql.com/downloads/mysql/进行下载`

```
            下载好后安装完，在终端上输入命令mysql --version查看MySQL下载的版本
```

![](https://img2018.cnblogs.com/blog/1177379/201906/1177379-20190613153338246-1008213550.png)

MySQL的启动与停止：

```
sudo 
/usr/
local
/mysql/
support-
files/mysql.server start
sudo 
/usr/
local
/mysql/
support-
files/mysql.server stop
```

在系统偏好设置中启动与停止MySQL服务

在系统偏好设置中有一个MySQL选项,我们可以在这里手动启动与停止MySQL服务

MySQL可视化管理方式phpMyAdmin：

[https://www.phpmyadmin.net/downloads/](https://www.phpmyadmin.net/downloads/)  phpmyadmin下载

下载完成后：将压缩文件解压到**/**资源库**/WebServer/Documents/**路径下,并重命名为phpMyAdmin

再次,将文件夹中的**config.sample.inc.php**文件重命名为**config.inc.php**

再次,将**config.inc.php**文件中的如下代码进行修改:讲 $cfg\['Servers'\]\[$i\]\['host'\] = 'localhost';修改为$cfg\['Servers'\]\[$i\]\['host'\] = '127.0.0.1';

最后,在浏览器中输入如下网址进行登录即可直接对MySQL进行可视化管理: [http://localhost/phpmyadmin/](http://localhost/phpmyadmin/)

默认用户名：root

安装路径：**usr/local/bin/mysql**

```
注：
因为在后期登陆phpmyadmin时忘记密码和每一次找回密码后下次在登陆上又会出现密码错误 解决方法：
```

解决登陆问题：每次密码都不同修改密码

第一步：点击系统偏好设置-&gt;最下边点mysql，在弹出的页面中，关闭服务

第二步：进入终端输入：cd/usr/local/mysql/bin

回车后登陆管理员权限：sudo su

./mysqld\_safe --skip-grant-tables &重启服务器

第三步：重开一个终端

```
          新终端下输入  alias mysql=/usr/local/mysql/bin/mysql

        输入mysql进入mysql命令

        use mysql进入mysql数据库

        flush privileges 获取权限
```

set password for 'root'@'localhost'=password\('新密码'\);完成修改



原文：[https://www.cnblogs.com/kyra/p/11017199.html](https://www.cnblogs.com/kyra/p/11017199.html)

