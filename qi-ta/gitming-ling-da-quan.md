## GIT命令大全

#### 切换账号

```
git config user.name//查看用户名
git config user.email//查看用户邮箱

//修改用户名和邮箱的命令
git config --global user.name "Your_username"
git config --global user.email "Your_email"
```

#### 创建分支

1\) 在本地创建dev分支、并切换到此分支

```
git checkout -b dev
```

2\) 上传本地分支到远程

```
git push origin dev
```

#### 把本地项目关联远程git项目

```
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/ucdbook/ddd.git
git push -u origin master

//查看远程地址
git remote -v

//删除与远程地址的关联
git remote remove origin
```

在github上看一个项目的大小

```
//在浏器打下以下Url地址
//ucdbook换成组件名
//Flutter-Music-Player换成仓库名
https://api.github.com/repos/ucdbook/Flutter-Music-Player
```



