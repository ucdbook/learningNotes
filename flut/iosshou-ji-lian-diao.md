## Mac下IOS手机调试

**步骤：**

1. 需要一个开发证书\(我用的是慧联开发证书\) ---\(图1\)
2. 把联调手机设备号加入开发证书中
3. mac安装开发证书\(双击安装.p12文件、两个.mobileprovision文件\) ---\(图2\)
4. 在xcode中配置证书、配置appId ---\(图3､图4\)
5. 构建项目：执行菜单栏Product &gt; Build
6. 启用项目---\(图5\)

---图1: 证书图片---

![](/assets/dsfdsfg.png)

---图2: 证书安装目录---

![](/assets/dsfdsggdh.png)

---图3: xcode配置appid---![](/assets/dsdfsgg.png)

---图4: xcode配置证书---![](/assets/dsgg.png)

---图5---![](/assets/dsdfsgdh.png)

**中途碰到的问题：**

一、证书装不上，提示“不能修改“System Roots”钥匙串”

解决方案：选择“登录”或login按钮---\(图2\)，直接将.cer/.p12文件拖进中间的各种钥匙列表中即可。

参考：[https://www.jianshu.com/p/f8c8293e59f3](https://www.jianshu.com/p/f8c8293e59f3)

二、项目在xcode中build时，提示iOS DeviceSupport版本不支持。后来升级了iOS DeviceSupport为版本13.2

升级方式: 下载需要的版本，复制到iOS DeviceSupport文件目录中

iOS DeviceSupport路径：![](/assets/dsfdsdfsf.png)

