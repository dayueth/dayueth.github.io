---
layout: post
title: "FinalShell无法连接谷歌云的解决方法"
subtitle: ' Solution to FinalShell unable to connect to Google Cloud'
author: "Zhy"
header-img: "img/in-post/post-liunx/1221header.jpg"
tags:
  - Liunx
  - 谷歌云
  - FinalShell
  - SSH
  - Google Cloud
---
 
## **前言**

无法通过SSH工具连接谷歌云的解决方法，我这里用的FinalShell，其他的工具方法大致也是一样的。

## **修改ssh配置文件并设置root密码**
**1.首先使用Google Cloud SSH登录VPS**  

![](/img/in-post/post-liunx/Snipaste_2022-12-21_17-20-47.png)



**2.切换到root账户**
```python
sudo -i
vim /etc/ssh/sshd_config   #编辑sshd配置文件
```
**3.修改一下内容即可**
按键盘【i】进入编辑，按【Esc】退出编辑，再输入 :wq 保存并退出

![](/img/in-post/post-liunx/122101.png)
![](/img/in-post/post-liunx/122102.png)

**3.重启sshd服务**
```python
service sshd restart 
passwd  #为root账户设置密码
```
输入密码的时候不会显示出来，所以直接输入密码，然后回车，再然后重复输入密码回车
![](/img/in-post/post-liunx/122103.png)  
这样就是设置成功了


## **用shell工具登录谷歌云实例**

**1.安装Finalshell连接工具**  
Win点击下载[Finalshell](http://www.hostbuf.com/downloads/finalshell_install.exe)，  
Mac点击下载[Finalshell](http://www.hostbuf.com/downloads/finalshell_install.pkg)  
下载完成后直接安装就好，使用其他的SSH工具也行。

**2.打开 Finalshell软件连接服务器**  
点击 【SSH连接Linux】  
![](/img/in-post/post-liunx/122104.png)  
输入账户和密码  
![](/img/in-post/post-liunx/122105.png)  
双击 登录  
![](/img/in-post/post-liunx/122106.png)  
点击【接受并保存】  
![](/img/in-post/post-liunx/122107.png)    
连接成功 
到这里就连接成功了，无法连接谷歌云的解决方法，其它的SSH连接工具也是大致相同的。 