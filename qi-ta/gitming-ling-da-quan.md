## GIT命令大全

#### 切换账号

```
git config user.name//查看用户名
git config user.email//查看用户邮箱

//修改用户名和邮箱的命令
git config --global user.name "Your_username"
git config --global user.email "Your_email"
```

创建分支

1\) 在本地创建dev分支、并切换到此分支

```
git checkout -b dev
```

2\) 上传本地分支到远程

```
git push origin dev
```



