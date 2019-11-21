Mac下IOS手机联调

**步骤：**

1. 需要一个开发证书\(我用的是慧联开发证书\)
2. 把联调手机设备号加入开发证书中
3. mac安装开发证书\(双击安装.p12文件、两个.mobileprovision文件\)
4. 在xcode中配置证书、配置appId

---证书图片---

![](/assets/dsfdsfg.png)

---证书安装目录---

![](/assets/dsfdsggdh.png)

---xcode配置证书---![](/assets/dsgg.png)

**中途碰到的问题：**

一、证书装不上，提示“不能修改“System Roots”钥匙串”

解决方案：选择“登录”或login按钮，直接将.cer/.p12文件拖进中间的各种钥匙列表中即可。

参考：[https://www.jianshu.com/p/f8c8293e59f3](https://www.jianshu.com/p/f8c8293e59f3)

二、项目在xcode中build时，提示iOS DeviceSupport版本不支持。后来升级了iOS DeviceSupport为版本13.2

升级方式: 下载需要的版本，复制到iOS DeviceSupport文件目录中

iOS DeviceSupport路径：![](/assets/dsfdsdfsf.png)

