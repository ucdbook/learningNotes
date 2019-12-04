## Flutter中使用图片

#### Material中自带Icon

#### [https://material.io/resources/icons/?icon=account\_balance&style=baseline](https://material.io/resources/icons/?icon=account_balance&style=baseline)

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

#### 引入本地图片：

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

#### 自定义图标字体:



