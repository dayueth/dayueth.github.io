---
layout: post
title: "[Python] pip network speed"
subtitle: ' Python pip 安装第三方库网速慢的解决方案'
author: "Zhy"
header-style: text
tags:
  - pip
  - Python
  - 软件基础
---

# Python Pip 安装第三方库网速慢的解决方案

## **前言**

Python之所以好用，并受到大家的喜爱，我想很多优质的第三方库是其中一个原因。例如爬虫我们使用的requests库，数据分析中的pandas库，机器学习中的sklearn库等。

* pandas
* numpy
* matplotlib 
* scipy
* sklearn
* ......

pip升级方式：

```
pip install pip -U
```


安装第三方库（其他库同理）：

```
pip install pandas
```

更新方式为：

```
pip install --upgrade pandas
```

但是你会发现，国外的源下载速度实在太慢，**容易下载超时**。要想加速安装第三方库，其实我们只需要使用国内的镜像即可。


## **国内镜像加速**

```python
清华：https://pypi.tuna.tsinghua.edu.cn/simple

阿里云：http://mirrors.aliyun.com/pypi/simple/

中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/

华中理工大学：http://pypi.hustunique.com/

山东理工大学：http://pypi.sdutlinux.org/ 

豆瓣：http://pypi.douban.com/simple/
```


### **临时使用**

```
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
```

### **设为默认**

升级 pip 到最新的版本 (>=10.0.0) 后进行配置：

``` 
pip install pip -U
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

设置成功后你的C:\Users\pip路径下会出现一个**pip.ini**配置文件如下图：

![图片](/img/in-post/post-Python/pip%20install.png)pip.ini配置文件及内容 

### **注意**

如果你的 pip 默认源的网络连接较差，可以临时使用清华的镜像站来升级 pip：

```python
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U
```