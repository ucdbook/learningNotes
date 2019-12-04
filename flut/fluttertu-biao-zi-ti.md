Flutter图标字体

#### Material中自带Icon

[https://material.io/resources/icons/?icon=account\_balance&style=baseline](https://material.io/resources/icons/?icon=account_balance&style=baseline)

用法：

```
//图片安扭
new IconButton(icon: new Icon(Icons.home), onPressed: _pushSaved)

//图片
Icon(Icons.add)
```

#### 引入本地图片：

```
Image.asset(
    'images/ic_home_light_tab.png',
    height: 24,
    width: 24,
)
```

#### 自定义图标字体:



