---
title: Ubuntu下使用SSR科学上网
date: 2019-07-12 20:59:08
tags: 
- tool
- ubuntu
categories:
- 生产力
comments: "true"

---

# Ubuntu下使用SSR科学上网



## 一、准备

- 操作系统：ubuntu14.04 及以上
- ssr：使用 ```electron-ssr-0.2.6```客户端
  下载地址：[点击下载](https://github.com/youngsw/ssr_Ubuntu)
<!-- more -->
## 二、安装

- 点击已经下载的` .deb`文件进行安装
- 安装完后如图
  ![ssr](/img/SsrUbuntu/ssr.jpg)
- 随后的操作和windows、Android下的操作一样，登录自己的账号就可舒舒服服的使用了google、youtube。
- ![google](/img/SsrUbuntu/google.png)

## 三、注意事项

- 如果登陆后没有成功的话，可能是因为PAC文件没有更新，此时在终端中使用```sudo electron-ssr```让其初始化即可。 
