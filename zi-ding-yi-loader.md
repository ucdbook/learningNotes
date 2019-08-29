## 自定义Loader

来看一个例子：

需求：把每个通过此loader编译的文件内容加上'console.log\("tianyanrong-----------"\);'

以下是myLoader.js文件:

```
module.exports = function(content, info) {
    const options = this.loaders[this.loaderIndex].options;
    console.log('loader options=', options); //loader options= { aaa: 1, bbb: 2 }
    content = content+'console.log("tianyanrong-----------");'
    return content;
}
```

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| content | String | 要编译的文件的内容，去掉空格、换行的内容 |
| info | Object |  |
| ----sources | \[String\] | 要编译的文件的地址，如：\[ '/Volumes/project/git/componentGo/app/index.tsx' \] |
| ----sourcesContent | \[String\] | 要编译的文件的内容, 原文件内容，带换行，空格等。 |

以下是webpack配置：

```
module: {
  rules: [
      {
        test: /index\.(ts|tsx)$/,
        exclude: /node_modules/,
        use: [
          {
            loader: path.resolve(myRoot, './bin/myLoader.js'),//loader.js文件地址
            options: {
              aaa: 1,
              bbb: 2
            }
          }
        ],
      },
    ]
  }
```



