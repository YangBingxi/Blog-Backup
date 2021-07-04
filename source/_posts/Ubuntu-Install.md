---
title: Ubuntu Install
date: 2020-01-01 10:09:24
tags: 
- tool
- ubuntu
categories:
- 生产力
comments: "true"
---

## Ubuntu Install

----------------------------------------------------------
### **Change sourse to ailiyun**

```bash
# 1.复制源文件备份，以防万一
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
# 2.编辑源列表文件
sudo vim /etc/apt/sources.list #请确保安装了vim，或者使用 sudo vi /etc/apt/sources.list
# 3.查看新版本信息
lsb_release -c
#Ubuntu 12.04 (LTS)代号为precise。
#Ubuntu 14.04 (LTS)代号为trusty。
#Ubuntu 15.04 代号为vivid。
#Ubuntu 15.10 代号为wily。
#Ubuntu 16.04 (LTS)代号为xenial。
#Ubuntu 18.04 (LTS)代号为bionic。
# 4.将原有的内容注释掉，添加以下内容，以Ubuntu18.04为例（或者你把里面内容修改成下面的就可以，但是不能有除了以下内容的有效内容，注意对应到你的版本）
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
# 5.更新软件列表
sudo apt-get update
# 6.更新软件包
sudo apt-get upgrade
```

<!-- more -->

----------------------------------------------------------
### **grub-customizer**

```bash
sudo add-apt-repository ppa:danielrichter2007/grub-customizer
sudo apt-get update
sudo apt-get install grub-customizer
```

----------------------------------------------------------
### **vim**

```bash
sudo apt update
sudo apt install vim
```

----------------------------------------------------------
### **Sougou Pinyin**

[link](https://pinyin.sogou.com/linux/?r=pinyin)

---

### **chrome**
[link](https://www.google.cn/chrome/)

----------------------------------------------------------
### **Ubuntu Cleaner**

```bash
sudo add-apt-repository ppa:gerardpuig/ppa
sudo apt update
sudo apt install ubuntu-cleaner
```

----------------------------------------------------------
### **ssr**
[link](https://github.com/youngsw/ssr_Ubuntu)

----------------------------------------------------------
### **wps**
[link](https://www.wps.cn/product/wpslinux)

```bash
#fix the problem of fonts:
	1.download the font,[link](https://github.com/youngsw/wps-fonts-)
	2.sudo cp * /usr/share/fonts
	3.sudo mkfontscale
	4.sudo mkfontdir
	5.sudo fc-cache
```

----------------------------------------------------------
### **IDEA**
[link](https://www.jetbrains.com/idea/)

----------------------------------------------------------
### **vsc**
[link](https://code.visualstudio.com/)

----------------------------------------------------------
### **mysql**

```bash
sudo apt update
sudo apt install mysql-server
```

```bash
 #if you don't set the password for root,it will be error while start it,you can fix it by:
1. (bash):sudo mysql -uroot -p #Use root login mysql
2. (mysql):update mysql.user set authentication_string=PASSWORD('newPwd'), plugin='mysql_native_password' where user='root';
3. (bash):sudo service mysql stop
4. (bash):sudo service mysql start
```

----------------------------------------------------------
### **mysql-workbench**

```bash
sudo apt update
sudo apt install mysql-workbench
```

----------------------------------------------------------
### **redis**

```bash
sudo apt update
sudo apt install redis-server
#test:
redis-cli
```



### **java**

```bash
1. download the jdk,link:https://www.oracle.com/technetwork/java/javase/downloads/index.html
2. cd /opt
3. sudo mkdir java
4. sudo cp jdk-*.tar.gz /opt/java
5. tar -zxvf jdk-*.tar.gz
6. sudo vim /etc/profile
7. add to the tail of the file
   #set java environment
   export JAVA_HOME=/opt/java/jdk-*
   export PATH=${JAVA_HOME}/bin:${PATH}
8. source /etc/profile
9. test
   java -version
```

----------------------------------------------------------
### **VLC (video player)**

```bash
sudo apt update
sudo apt install vlc
```

----------------------------------------------------------
### **CHM reader**

```bash
sudo apt update
sudo apt-get install xchm
```

----------------------------------------------------------
### **peek**

```bash
sudo add-apt-repository ppa:peek-developers/stable
sudo apt update
sudo apt-get install peek
```

----------------------------------------------------------
### **gitkraken**
[link](https://www.gitkraken.com/download/linux-deb)

----------------------------------------------------------
### **hexo** 

```bash
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm

nodejs -v
npm -v

mkdir hexo
cd hexo
sudo npm install -g hexo-cli
hexo init

# if have error,do this:
sudo npm config set user 0
sudo npm config set unsafe-perm true
sudo npm install -g hexo-cli


/***********************************************************************************/
Write blog:
Step1: 
    hexo new post "article title" //Create a new .md file and a new folder to save it img.
Step2:
    //Write your blog in your file which is just create.
Step3:
    hexo g //Create static web.
    hexo s //Start the server,and then you can preview your blog in your browser with "localhost:4000".
    hexo d //put your new Blog qo your github if you had linked to your github.
*/
```

### **trash-cli**

```bash
sudo apt install trash-cli
```

### figlet

```bash
sudo apt install figlet
```



__By SwYoung