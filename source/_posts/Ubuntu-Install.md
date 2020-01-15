---
title: Ubuntu Install
date: 2020-01-01 10:09:24
tags: 工具
comments: "true"
---

## Ubuntu Install

----------------------------------------------------------
+ **Change sourse to ailiyun**
----------------------------------------------------------
+ **grub-customizer**

  ```bash
  sudo add-apt-repository ppa:danielrichter2007/grub-customizer
  sudo apt-get update
  sudo apt-get install grub-customizer
  ```
----------------------------------------------------------
<!-- more -->
+ **vim**

  ```bash
  sudo apt update
  sudo apt install vim
  ```
----------------------------------------------------------
+ **SpaceVim**

  ```bash
  curl -sLf https://spacevim.org/install.sh | bash
  ```
----------------------------------------------------------
+ **Sougou Pinyin**
+ [link](https://pinyin.sogou.com/linux/?r=pinyin)

---

+ **chrome**
[link](https://www.google.cn/chrome/)
----------------------------------------------------------
+ **Ubuntu Cleaner**

  ```bash
  sudo add-apt-repository ppa:gerardpuig/ppa
  sudo apt update
  sudo apt install ubuntu-cleaner
  ```
----------------------------------------------------------
+ **ssr**
[link](https://github.com/youngsw/ssr_Ubuntu)
----------------------------------------------------------
+ **wps**
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
+ **IDEA**
----------------------------------------------------------
+ **Eclipse**
----------------------------------------------------------
+ **mysql**

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
+ **mysql-workbench**

  ```bash
  sudo apt update
  sudo apt install mysql-workbench
  ```
----------------------------------------------------------
+ **redis**

  ```bash
  sudo apt update
  sudo apt install redis-server
  #test:
  redis-cli
  ```

  

+ **java**

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
+ **VLC (video player)**

  ```bash
  sudo apt update
  sudo apt install vlc
  ```
----------------------------------------------------------
+ **CHM reader**

  ```bash
  sudo apt update
  sudo apt-get install xchm
  ```
----------------------------------------------------------
+ **peek**

  ```bash
  sudo add-apt-repository ppa:peek-developers/stable
  sudo apt update
  sudo apt-get install peek
  ```
----------------------------------------------------------
+ **gitkraken**
[link](https://www.gitkraken.com/download/linux-deb)
----------------------------------------------------------
+ **hexo** 

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

  ​																																					__By SwYoung
