---
title: JDK安装教程
date: 2018-04-15 14:53:32
tags: Java
categories: 技术分享
---

学习Java，首先得安装JDK(Java Development Kit)，那么下面就说一下如何在Windows和Linux下安装并验证JDK。


# JDK的下载
JDK的官方下载地址为： http://www.oracle.com/technetwork/java/javase/downloads/index.html， 请根据需要下载对应操作系统的安装包。
> 官方下载速度比较慢，因此可以从华为开源镜像站下载，地址为：https://mirrors.huaweicloud.com/repository/toolkit/java/jdk/

# Windows下安装JDK
+ 以`jdk-8u151`为例，**双击上一步下载下来的exe文件**，默认安装即可。（备注：路径可以选择其他盘符，但是不建议路径中包含中文及特殊字符）
+ 安装好之后需要设置环境变量，进入到系统环境变量的管理界面：`右键计算机图标=>属性=>高级系统设置=>环境变量`
{% asset_img windows_install_01.png [设置Windows环境变量] %}
+ `新建`变量`JAVA_HOME`，变量值：`C:\Program Files\Java\jdk1.8.0_151`(地址请根据自身情况进行修改)
+ `编辑`变量`PATH`，在`最前边`增加：`%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;`
+ `新建`变量`CLASSPATH`，变量值：`.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar`
{% asset_img windows_install_02.png [设置Windows环境变量] %}

- [x] 已完成任务一
- [x] 已完成任务二
- [x] 已完成任务三
- [ ] 未完成任务四
- [ ] 未完成任务五

# Linux下安装JDK
1. 以`jdk-8u151`为例，下载JDK后，将压缩包解压至特定的目录，一般解压至/usr/local目录，下载和解压命令可以参考如下命令：
```
wget https://mirrors.huaweicloud.com/repository/toolkit/java/jdk/8u151-b12/jdk-8u151-linux-x64.tar.gz
tar -zxvf -C /usr/local/ jdk-8u151-linux-x64.tar.gz
```

```javascript
dsfdsfsfs"fsfsfdsf"
```


-----------------

2. 经JDK的路径加入到环境变量中，在命令行中输入`vim /etc/profile`，编辑文件，在文件末尾增加如下的内容，然后执行`source /etc/profile`使环境变量生效。
```
export JAVA_HOME=/usr/local/jdk-8u151
export JRE_HOME=/usr/local/jdk-8u151/jre
export CLASS_PATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib
export PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin
```

# JDK的验证
windows打开`CMD`命令窗口，Linux打开终端端口，输入`java -version`命令，如果出现如下提示则Java安装成功。
{% asset_img jave_version.png [Java的验证] %}


