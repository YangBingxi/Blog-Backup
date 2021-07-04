---
title: Linux下如何避免误删文件
date: 2020-01-23 20:01:37
tags: 
- linux
- tool
categories:
- 生产力
---

## Linux下如何避免误删文件

### 前言

在Linux的使用中，我们会有这样的惨痛经历：用rm不小心删除了某个文件却再也找不回来，只能在痛苦和悔恨中再次码字。当然rm误删文件在桌面版的Linux中还是比较容易处理，只要去Trash文件夹中找回即可，但是如果操作的服务器，那就不好办了。

下面我给大家推荐几个方法，可以有效的减少这种麻烦的产生。

<!-- more -->

### 预防方法

#### 改变使用rm的习惯

- 建立一个文件夹，用来存储被“删除”的文件，如Trash
- 再以后的使用中，遇到删除的东西，只要使用mv指令，移动到Trash文件夹即可

#### trash-cli

##### 软件介绍

trash-cli是命令行下可以用来管理垃圾文件的一个软件

##### 安装

```bash
sudo apt install trash-cli
```

##### 使用

```bash
trash 待删除的文件 #删除某个文件
trash-put 待删除的文件  #与trash一样，删除某个文件
trash-empty #清空回收站
trash-list #列出回收站
restore-trash #恢复文件，根据提示的编号进行恢复
trash-rm  #删除回收站中指定文件
```

##### 说明

可以根据自身需要进行命令的软连接

如：```alias rm='trash'```将rm指令链接为trash操作
