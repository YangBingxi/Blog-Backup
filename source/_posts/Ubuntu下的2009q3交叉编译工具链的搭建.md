---
title: Ubuntu16.04下的2009q3交叉编译工具链的搭建
date: 2018-07-11 08:04:14
tags: 工具
comments: "true"
---

# Ubuntu16.04下的2009q3交叉编译工具链的搭建

###  

### 环境搭建：

   1.下载`arm-2009q3.tar.bz2`源码。

 [百度云链接](https://pan.baidu.com/s/1jJnzh3o)  密码: rbui

   2.将`arm-2009q3.tar.bz2`拷贝到/usr/local/arm(没有该目录就新建一个)目录下,执行命令`tar jxvf arm-2009q3.tar.bz2`进行解压。
<!-- more -->
   3.为了能在别的路径下运行需要修改环境变量

  执行命令`vim ~/.bashrc`（若提示权限不够，在命令前加上`sudo`即可）   在文件末尾加上`export PATH=/usr/local/arm/arm-2009q3/bin:$PATH`（注意路进正确性，如果此路径运行后不行的话可以尝试`export PATH=/usr/arm/arm-2009q3/bin:$PATH`）
  执行命令`source ~/.bashrc`

到此路径已修改完成

   4.安装32位库

  因为ia32-libs数据库的问题需安装32位库   依次执行下列命令即可

```
sudo dpkg --add-architecture i386   
sudo apt -get update  
sudo apt-get dist-upgrade  
```

  到此Ubuntu16下的2009q3交叉编译工具链的搭建已完成 执行命令`arm-none-linux-gnueabi-gcc -v`检查工具的链是否搭建成功。

   By Sw Young
