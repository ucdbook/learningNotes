## 如何使用图片

#### Material中自带Icon

所有图标：[https://material.io/resources/icons/?icon=account\_balance&style=baseline](https://material.io/resources/icons/?icon=account_balance&style=baseline)

pubspec.yaml中配置：

```
flutter:

  uses-material-design: true
```

调用：

```
//图片安扭
new IconButton(icon: new Icon(Icons.home), onPressed: _pushSaved)

//图片
Icon(Icons.add)
```

#### 引入本地图片

pubspec.yaml中配置：

```
flutter:

  uses-material-design: true

  assets:
    - lib/images
```

调用：

```
Image.asset(
    'images/ic_home_light_tab.png',
    height: 24,
    width: 24,
)
```

#### 使用远程图片

```
Image.network(
    'http://portal.etransfar.com/hrPortal/images/login/pic_1.png',
    height: 24,
    width: 24,
)
```

#### 使用外部图标字体

pubspec.yaml中配置：

```
flutter:

  uses-material-design: true

  assets:
    - lib/images

  fonts:
    - family: FontAwesome
      fonts:
        - asset: lib/fonts/FontAwesome.ttf
```

调用：

```
Icon(
  IconData(
     61447,//code
     fontFamily: 'FontAwesome'//字体
  ),
  color: Colors.red,
）
```

## 图片的样式控制

各种圆角图片：[https://blog.csdn.net/weixin\_44862319/article/details/88993060](https://blog.csdn.net/weixin_44862319/article/details/88993060)

## 



