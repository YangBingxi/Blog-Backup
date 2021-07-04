---
title: 解决 nginx 413 Request Too Large
date: 2020-02-16 19:45:05
tags:
- nginx
- linux
- 网站
categorie:
- 后端
- code
- 服务器
---
## 解决 nginx 413 Request Too Large

### 说明
在服务器上使用nginx的时候出现413错误。因有可能是nginx设置了上传大小限制。

<!-- more -->

### 解决方法
- 打开nginx的配置文件```nginx.conf```,文件路径是 ```/etc/gninx```
- 在```http{}```配置端中添加
```
client_max_body_size 20m;
```

- 重启nginx服务```server nginx restart```


