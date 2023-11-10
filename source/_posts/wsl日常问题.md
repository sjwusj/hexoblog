---
title: wsl日常问题
date: 2023-11-06 22:18
tags:
  - Linux
  - Wsl
categories:
  - Linux
cover: image/cover2.jpg
---

系统：Ubuntu-20.04

平台：WSL2



wsl2平台启用ssh服务：sudo /etc/init.d/ssh start

linux可以使用ssh客户端连接其他服务器：ssh  用户名@xxx.xxx.xxx.xxx

日志：/var/log 文件夹下

宝塔面板：sudo bt default 显示密码和入口网址



**创建用户没有在/home目录下生成对应目录**

- 前提：sudo useradd milan
- 操作切换用户：su - milan
- 报错：su: warning: cannot change directory to /home/milan: No such file or directory
- 解决方法：

```zsh
#退出并转换到home目录下
exit
cd /home

#创建对应用户名文件夹
sudo mkdir /home/milan

#设置权限
r=4 w=2 x=1
sudo chmod 755 /home/milan

#初始化
sudo cp -a /etc/skel/.  /home/milan
```



**限制wsl2占用过多内存**

[限制wsl2占用过多内存 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/345645621)

在powershell中重启wsl2：wsl --shutdown

- 如果我们直接关闭`wsl2`的窗口并不会关闭该`wsl2`的虚拟机，它依旧会在后台运行，需要关闭wsl2的话我们可以打开`powershell`，在里面使用`wsl --shutdown`命令就可以关闭全部的`wsl2`虚拟机了。之后再随意打开一个wsl2的窗口就会再次开启虚拟机。

- 这种方式释放内存最彻底，效果和物理机内存不足卡死然后直接重启是一样的。



**FinalShell连接报错**

问题：

- 连接主机...
  java.net.ConnectException: Connection refused: connect

解决：

- 查看ssh设置的端口
  命令：vi /etc/ssh/sshd_config

- 重启ssh
  命令：systemctl restart  sshd

- 或者：/etc/init.d/ssh  start



**wsl文件目录**

wsl和wsl2的文件目录有所不同

[windows10 Linux子系统(wsl)文件目录_子系统显示在目录里_天已青色等烟雨来的博客-CSDN博客](https://blog.csdn.net/x356982611/article/details/80077085)

wsl

- [ubuntu](https://so.csdn.net/so/search?q=ubuntu&spm=1001.2101.3001.7020) Linux子系统的目录是在这个目录下

```
C:\Users\用户名\AppData\Local\Packages\CanonicalGroupLimited.UbuntuonWindows_79rhkp1fndgsc\LocalState\rootfs
```

wsl2

- wsl2的linux的文件系统整个是个镜像文件，启动系统后，这个文件系统映射到了 `\\wsl$\系统名` 下面   \\wsl$\Ubuntu-20.04\
- 一开始安装在在哪个盘中，镜像文件ext4.vhdx就在哪个盘中

![image-20230831104755455](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20230831104755455.png)



**WSL备份虚拟机**

[WSL2 Ubuntu-20.04文件太占c盘空间，使用导入导出来实现位置挪移，移动到d盘下面 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/510650353#:~:text=WSL2 Ubuntu-20.04文件太占c盘空间，使用导入导出来实现位置挪移，移动到d盘下面 在windows运行中输入,%localappdata%Packages 找到 CanonicalGroupLimited.Ubuntu20.04LTS开的文件夹，可见这个文件夹很大，这个就是虚拟机的文件存放地。)

[简单到极致！Windows 10 Ubuntu子系统的备份/还原教程来了 - 简书 (jianshu.com)](https://www.jianshu.com/p/8b4ec8fafdca)

```
#停止子系统
wsl -t Ubuntu-20.04

#备份
wsl --export Ubuntu-20.04 F:\Linux\Ubuntu-20.04.tar(或者.bak顶等等)

#还原
wsl --import Ubuntu-20.04 c:\WSL F:\Linux\Ubuntu-20.04.tar
```



**Ubuntu系统下安装rpm安装包**

[Ubuntu系统下安装rpm安装包_ubuntu rpm_码农研究僧的博客-CSDN博客](https://blog.csdn.net/weixin_47872288/article/details/120771718)

Ubuntu的软件包格式为deb
而RPM格式的包归属于红帽子Red Hat
在这直接使用命令是安装不了的
需要通过一个桥梁进行转换

```
#将其rpm的格式包转换为deb的格式包
#具体转换通过alien进行转换
sudo apt-get install alien 
```

```
#通过这个命令将其转换
sudo alien xxxx.rpm
```

```
#安装deb包
sudo dpkg -i xxxx.deb
```



**Ubuntu包管理工具整理**

[Ubuntu包管理工具整理 - weaming - 博客园 (cnblogs.com)](https://www.cnblogs.com/weaming/p/5079032.html#:~:text=Ubuntu包管理工具整理 1 apt 包含了很多工具，apt-get 主要负责软件包的在线安装与升级，低层对 deb 包的处理还是用的 dpkg,可以离线安装软件包，apt-build 可以简化源码编译等等，有兴趣可以学习一下 apt 开头软件包。 ... 3 aptitude 是更强大的安装工具，有两种基本的使用方法，一种是文本界面，另一种是命令行，这里只讨论命令行操作。)

[Ubuntu软件包管理器 - 被罚站的树 - 博客园 (cnblogs.com)](https://www.cnblogs.com/xidongyu/p/7801897.html#:~:text=安装软件：dpkg -i 移除软件：dpkg -r 查看某个软件包是否已经安装：dpkg -l 查看某个软件包中都包含哪些文件：dpkg,-L 查看系统中的某个文件是由哪个软件包提供的： dpkg -S %2Fpath%2Fto%2Ffile 查看哪些软件包未完成安装：dpkg -C)

 Ubuntu与Cenots的关系：[Ubuntu之软件包管理 (最全最精) - 梨花海棠 - 博客园 (cnblogs.com)](https://www.cnblogs.com/xunweidezui/p/14591024.html)

- 常用的包管理包含三类工具：dpkg、apt

- 软件包后缀
  centos：  *.rpm
  Ubuntu ：*.deb



**Ubuntu搭建JavaEE开发环境**

[ubuntu 搭建 JavaEE 开发环境_lrkhh的博客-CSDN博客](https://blog.csdn.net/qq_36405385/article/details/105750023)

JDK

- Linux 下 JDK 到底应该 安装 在哪儿？. 最标准的 jdk安装 路径是 **/usr/local/java/** jdk 1.6.0_38 /usr/local/java/ jdk 1.8.xxx 注意：几个不同的 jdk 可以共存，都放在/usr/local/java/下 然后在/etc/profile里面export JAVA_HOME指定默认的 jdk

- /etc/profile和~/ .profile和/etc/profile.d的区别：

  [Linux下JDK到底应该安装在哪儿？_hellocsz的博客-CSDN博客](https://blog.csdn.net/hellocsz/article/details/82701380#/usr/local/java/jdk1.8.xxx)

Tomcat

- Linux启动tomcat报错

```
Neither the JAVA_HOME nor the JRE_HOME environment variable is defined
At least one of these environment variable is needed to run this program
```

- 解决方法一：[Linux启动tomcat报错：Neither the JAVA_HOME nor the JRE_HOME environment variable is defined_渐暖°的博客-CSDN博客](https://blog.csdn.net/yujing1314/article/details/94350446)

  - sudo vim setclasspath.sh 

    setclasspath.sh文件在/opt/tomcat/apache-tomcat-8.5.59/bin下(根据自己的Tomcat存放位置来)

  - ![image-20230831224612202](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20230831224612202.png)

- 解决方法二：[Ubuntu18.04 安装Tomcat 8.5 - 捷后愚生 - 博客园 (cnblogs.com)](https://www.cnblogs.com/Uni-Hoang/p/12945205.html)
  - sudo vim startup.sh
  - ![image-20230831231532157](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20230831231532157.png)
- [Ubuntu下设置Tomcat开机自启动](https://www.cnblogs.com/wang-jx/p/13038542.html)

MySql

- [Ubuntu 20.04 安装和配置MySql5.7](https://www.cnblogs.com/lian95/p/14140838.html)

- [Ubuntu20.04中安装MySQL 5.7.x - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/348317883)

- [Ubuntu20.04安装MySQL5.7-实测3种方法（保姆级教程）_liuhuango123的博客-CSDN博客](https://blog.csdn.net/liuhuango123/article/details/128264867)
- [Ubuntu 20.04 安装和配置MySql5.7 - Wly球球 - 博客园 (cnblogs.com)](https://www.cnblogs.com/lian95/archive/2020/12/17/14140838.html#:~:text=Ubuntu 20.04 安装和配置MySql5.7 1 1. Ubuntu换源 ubuntu 20.04系统自带源直接安装是MySQL,5. Navicat 远程连接数据库 ... 6 6. 卸载mysql )
- **忘记mysql5.7的ROOT用户密码**：https://www.bilibili.com/video/BV1Sv411r7vd?t=83.5&p=143



**Ubuntu重启或新窗口遇到环境未配置问题**

问题

- 默认为bash，在/etc/profile中配置后，在bash中生效，但若使用zsh，重启之后配置在/etc/profile的环境会失效

解决：

- vim  .zshrc
- ![image-20230901103635109](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20230901103635109.png)



**bash 切换到 zsh 环境变量丢失问题**

解决办法 ：[bash 切换到 zsh 环境变量丢失问题 - 简书 (jianshu.com)](https://www.jianshu.com/p/a3e0bb16675e)

​	1 、在bash下面执行:
​		 `echo $PATH`
​		 查看系统路径，复制路径。
​	 2、然后切换到zsh,
​		 `sudo vim ~/.zshrc`
​		 在 #*If you come from bash you might have to change your $PATH.*下面添加刚才的路径:
​		 `export PATH=" you path copy just now "`
​	 3、退出文件，在zsh下执行:
​		 `source ~/.zshrc`
​		 初始化配置文件。
 		搞定，以上。

[ubuntu 环境变量 失效的解决办法_ubantu 环境变量怎么自己没了_Lincoln_XDU的博客-CSDN博客](https://blog.csdn.net/u012146107/article/details/11766797)

Ubuntu包含两种环境变量：系统，用户，使用bash情况下

用户环境变量：

~/.profile

~/.bash_profile 或者 ~./bash_login

~/.bashrc

系统环境变量：

/etc/environment

/etc/profile

/etc/bash.bashrc




**如何解决win10 子系统用wsl安装ubuntu22.04不能用systemctl?**

[(30 封私信 / 80 条消息) 如何解决win10 子系统用wsl安装ubuntu22.04不能用systemctl? - 知乎 (zhihu.com)](https://www.zhihu.com/question/535145130)



**基于windows WSL安装Docker Desktop**

修改默认安装到C盘及默认下载镜像到C盘

[基于windows WSL安装Docker Desktop，修改默认安装到C盘及默认下载镜像到C盘-腾讯云开发者社区-腾讯云 (tencent.com)](https://cloud.tencent.com/developer/article/2127691)

修改默认安装到C盘

- 删除如下目录C:\Program Files\[Docker](https://cloud.tencent.com/product/tke?from_column=20065&from=20065)
- 在D盘新建目录：D:\Program Files\Docker
- win+r，运行cmd
- 在cmd中执行如下命令：`mklink /j "C:\Program Files\Docker" "D:\Program Files\Docker"`
- 执行下载的安装程序，即可将Docker Desktop安装到D盘了

修改镜像默认下载到C盘

- 新建目录 D:\ProgramData\Docker
- 将 C:\Users\你的用户名\AppData\Local\Docker下的所有文件copy到 D:\ProgramData\Docker
- 删除目录 C:\Users\你的用户名\AppData\Local\Docker
- 在C:\Users\你的用户名\AppData\Local下执行`cmd /c mklink /J Docker D:\ProgramData\Docker`
- 上述命令是在powershell下执行，若是在cmd下执行则如下`mklink /J Docker D:\ProgramData\Docker`

![image-20230902162154706](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20230902162154706.png)



**docker | 基于 WSL2 在 Windows 下使用 docker**

[docker | 基于 WSL2 在 Windows 下使用 docker - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/475022079)

[Docker-Docker Desktop 安装教程，以及推荐Docker作为学习工具的理由_docker desktop安装_xiaoliizi的博客-CSDN博客](https://blog.csdn.net/xiaoliizi/article/details/118438413)

配置镜像

- ![image-20230902163010819](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/image-20230902163010819.png)