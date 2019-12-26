dart中文学习笔记：[https://www.yiibai.com/dart/dart\_programming\_syntax.html](https://www.yiibai.com/dart/dart_programming_syntax.html)

dart官网\(库的介绍\)：[https://api.dartlang.org/stable/2.6.1/dart-io/dart-io-library.html](https://api.dartlang.org/stable/2.6.1/dart-io/dart-io-library.html)

一、数字类型包含哪些：

a. double     b. int      c. String     d. Set

二、声明变量的方式

a. var        b. 数据类型前缀        c. Dart         d. const            e. void           f. let

三、以下函数不正确写法的是

A.

```
void aa = () => print('ddd');
```

B.

```
void aa = () => {
    print('ddd');
    print('cccc');
};
```

C.

```
void aa = () {
    print('ddd');
    print('cccc');
};
```

D.

```
void _createComparsionFunction(String propertyName) {
  return (object1, object2) {
    var value1 = object1[propertyName];
    var value2 = object2[propertyName];
    if (value1 < value2) {
      return -1;
    } else if (value1 > value2) {
      return 1;
    } else {
      return 0;
    }
  };
}
```

四、函数的传参

五、定时器

六、Map、LIst读取、设置

七、字符串与数值的转换

```
var a = int.parse('1234');         //把字符串 1234 转换成 数值 1234
print(a is int);                   //判断是否转换成功
//输出 ture 

var b = double.parse('1234.12');  //把字符串 1234.12 转换成 数值 1234.12
print(b is double);               //判断是否转换成功
//输出 ture 

var str = 1234.toString();        //把数值 1234 转换成 字符串 1234
print(str  is String);            //判断是否转换成功
//输出 ture 

```



