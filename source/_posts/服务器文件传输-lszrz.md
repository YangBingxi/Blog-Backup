---
title: 服务器文件传输-lszrz
comments: "true"
date: 2021-07-04 15:06:27
tags:
- linux
categories:
- Code
---

## 服务器文件传输-lszrz

### 【说明】在linux服务器端，使用lszrz工具，快速上传或者下载文件。

<!-- more -->

### 一、安装lszrz

```shell
sudo apt install lrzsz
```

或者

```shell
yum install lrzsz
```



### 二、使用

#### 下载文件：sz中的s意为send（发送），告诉客户端，我（服务器）要发送文件 send to client，就等同于客户端在下载。

```shell
sz filename 
```

#### 上传文件： rz中的r意为received（接收），告诉客户端，我（服务器）要接收文件 received by cilent，就等同于客户端在上传。

```shell
rz #输入rz后会有弹窗提示选取文件
```

