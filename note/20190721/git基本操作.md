# git基本操作

## 1、设置邮箱、用户名

设置邮箱：

```shell
git config --global user.email "邮箱"
```

设置用户名：

```shell
git config --global user.name  "用户名"
```

## 2、生成SSH Key方法

首先查看.ssh文件夹，看是否有具体的公钥私钥信息文件。

```shell
cd ~/.ssh
ll
```

若无相应的id_rsa、id_rsa.pub文件，则需要通过以下命令生成：

```shell
ssh-keygen -t rsa -C "youremail@example.com"
```

> 指令介绍
>
> t ：类型
>
> C：备注，一般输入邮箱



## 3、初始化git仓库

创建一个目录

```shell
mkdir test
```

进入该目录，使用`git init` 命令初始化该仓库

```shell
cd test
git init
```

## 4、创建文件并添加到`git`仓库

添加文件

```shell
touch 文件名
```

使用git add命令将文件添加到git仓库

```shell
git add 文件名
```

## 5、 查看仓库状态

使用`git status` 查看仓库状态

```shell
git status
```



## 6、查看仓库日志

使用`git log`命令来查看仓库的提交日志，若后面跟指定的文件名，则仅查看该文件的日志。

```shell
git log //查看仓库所有文件的提交日志
git log 指定的文件名 //查看仓库具体文件的提交日志
```



## 7、从git仓库里删除文件

一般使用`git rm`命令来删除具体的文件，不建议直接执行`git rm`命令，会导致当前目录下的所有的文件都会被删掉。

从文件夹中删除目录（并不会更新到git仓库）：

```shell
rm 指定的文件名
```



```shell
git rm 指定的文件名
```



## 8、提交

提交主要通过`git commit`命令来将现有工作区中的文件更新到版本库。

```shell
git commit -m "提交"
```

指令解释:

> m ：注释，可通过git log 查看到该注释



## 9、从远程仓库克隆至本地

进入想要存放该仓库的目录

```shell
cd 目录
```

通过`git clone`命令将远程仓库克隆至本地

```shell
git clone 仓库地址  //仓库地址如：git@github.com:chenghy/tester.git
```

## 10、从远程仓库拉取文件

一般修改文件前， 先从git远程仓库里拉取文件，使当前本地git仓库和远程版本尽量保持一致。

```shell
git pull
```

## 11、推送文件

修改本地文件后，需要将本地修改的文件推送至远程仓库。

```shell
git push
```



