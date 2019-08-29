自定义Loader

来看一个例子：

需求：把每个通过此loader编译的文件内容加上'console.log\("tianyanrong-----------"\);'

以下是myLoader.js文件:

```
module.exports = function(content, fileInfo) {
    const options = this.loaders[this.loaderIndex].options;
    console.log('loader options=', options); //loader options= { aaa: 1, bbb: 2 }
    content = content+'console.log("tianyanrong-----------");'
    return content;
}
```

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



