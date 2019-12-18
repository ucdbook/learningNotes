一、使用http插件发送请求

[https://pub.flutter-io.cn/packages/http](https://pub.flutter-io.cn/packages/http)

第一步：pubspex.yaml中配置依赖

```
dependencies:
  flutter:
    sdk: flutter
  ...
  http: ^0.12.0+2
```

第二步：

在项目中封装http方法, 进行业务需求的请求前、请求完成后的拦载工作。如

```

```

二、给H5配置接口代理

```
dev_dependencies:
  ...
  build_runner: ^1.6.2
  build_web_compilers: ^2.0.0
```

```
//安装webdev
flutter pub global activate webdev
```

```
/* mac中配置webdev的环境变量 */
//打开环境变量文件
vi ~/.bash_profile

//写入webdev路径(路径在安装完webdev后，会有提示，如下图)
export PATH="$PATH":"/Volumes/project/flutter/.pub-cache/bin"
```

![](/assets/4433344.png)

三、给H5配置热加载

