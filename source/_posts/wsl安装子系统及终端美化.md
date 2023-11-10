---
title: wsl安装子系统及终端美化
date: 2023-11-06 21:35
tags: Linux
abstracts: windows专业版启用wsl安装linux子系统并且对终端进行美化
cover: image/cover1.jpg
---
# 安装

官方文档

- [安装 WSL |Microsoft学习](https://learn.microsoft.com/en-us/windows/wsl/install)


微软商店下载**Windows Terminal 应用程序**，如果喜欢原装可以忽略

1. [如何在 Windows 10 上安装 WSL 2 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/337104547)

### 第 1 步，启用 WSL

不管您想要使用哪个版本的 WSL，都首先需要启用它。为此，请**以管理员身份打开 PowerShell 工具并运行以下命令**。小心不要在命令中输入错误或遗漏任何字符：

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

### 第 2 步，启用“虚拟机平台”

WSL 2 需要启用 Windows 10 的 “虚拟机平台” 特性。它独立于 Hyper-V，并提供了一些在 Linux 的 Windows 子系统新版本中可用的更有趣的平台集成。

要在 Windows 10（2004）上启用虚拟机平台，请以管理员身份打开 PowerShell 并运行：

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

要在 Windows 10（1903，1909）上启用虚拟机平台，请以管理员身份打开 PowerShell 并运行：

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform -NoRestart
```

为了确保所有相关部件都整齐到位，您应该在**此时重启系统**，否则可能会发现事情没按预期进行。

### 第 3 步，设置 WSL 2 为默认值

以管理员身份打开 PowerShell，然后运行以下命令以将 WSL 2 设置为 WSL 的默认版本：

```powershell
wsl --set-default-version 2
```

如果需要，您可以（随时）将发行版配置为以 WSL 1 模式运行

### 第 4 步，安装一个 Linux 发行版

默认安装为c盘，如果c盘空间不够建议安装在其他盘



2. 参考[Windows10/11 三步安装wsl2 Ubuntu20.04（任意盘） - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/466001838)

首先先在你喜欢的盘创建一个文件夹，比如D:\Linux ，因为这样即便是重装系统我也不用重新装软件。

然后进到这个文件夹 下载ubuntu20.04

```
Invoke-WebRequest -Uri https://wsldownload.azureedge.net/Ubuntu_2004.2020.424.0_x64.appx -OutFile Ubuntu20.04.appx -UseBasicParsing
```

然后执行下面四条命令。如下图

```text
Rename-Item .\Ubuntu20.04.appx Ubuntu.zip
Expand-Archive .\Ubuntu.zip -Verbose
cd .\Ubuntu\
.\ubuntu2004.exe
```

3. 安装其他发行版方法[自定义WSL的安装位置，别再装到C盘啦 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/263089007)

# 美化

参考[WSL2 搭建 Windows 更好用的前端开发环境 | CodecWang](https://codec.wang/blog/setup-wsl-for-frontend)

[用 WSL2 搭建 Windows 上更爽的前端开发环境_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1BV4y1Z7v4/?spm_id_from=333.1007.top_right_bar_window_default_collection.content.click&vd_source=0bbd99419aa302dfd5e8f27118f9516d)

```linux
# 更新 package
sudo apt update && sudo apt upgrade

# 安装 zsh
sudo apt install zsh -y

# 安装 oh-my-zsh
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true

# 安装命令补全和高亮插件
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/plugins/zsh-autosuggestions
sed -i 's/plugins=(git)/plugins=(git zsh-autosuggestions zsh-syntax-highlighting)/g' ~/.zshrc

# 将 zsh 设置为默认的shell
chsh -s /bin/zsh
```

安装on-my-zsh参考 https://blog.csdn.net/qwe641259875/article/details/107201760

[Ubuntu 下 Oh My Zsh 的最佳实践「安装及配置」 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/38061286)



简单配置

[windows 10 安装子系统(WSL2) - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/406986986)

### **针对ubuntu系统进行简单的配置**

1. 查看ubuntu版本,我是用的最新的
   lsb_release -a

![img](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/v2-00907f37f4dacb63b6328a4ae35b5933_720w.webp)



1. 配置root密码
   \#ubuntu默认情况下只能普通用户登录,需要给root设置密码才能使用,命令如下
   sudo passwd root
2. 配置国内源
   \#由于软件源是国外的,安装软件时比较慢,需要改成国内源,如果阿里,中科大,清华,163源都 是可以的

- 建议先备份 下原来的文件
  \#备份文件
  cp /etc/apt/sources.list /etc/apt/sources.list.bak
- 替换成国内的源
  vim /etc/apt/sources.list
  \#这里有的系统里没有vim这个工具,可以使用
  apt-get install vim
  \#也可以直接使用vi进行操作

![img](https://cdn.jsdelivr.net/gh/sjwusj/imgbed@main/img/v2-778a11431c257b057599ff28c5fd34ea_720w.webp)



```text
国内源如下
#清华镜像
 https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal main restricted universe multiverse deb
 https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-updates main restricted universe multiverse deb 
https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-backports main restricted universe multiverse deb 
https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ focal-security main restricted universe multiverse 
#中科大 
 https://mirrors.ustc.edu.cn/ubuntu/ focal main restricted universe multiverse deb
 https://mirrors.ustc.edu.cn/ubuntu/ focal-security main restricted universe multiverse deb 
https://mirrors.ustc.edu.cn/ubuntu/ focal-updates main restricted universe multiverse deb
 https://mirrors.ustc.edu.cn/ubuntu/ focal-backports main restricted universe multiverse 
#163软件源 
 http://mirrors.163.com/ubuntu/ wily main restricted universe multiverse deb
 http://mirrors.163.com/ubuntu/ wily-security main restricted universe multiverse deb
 http://mirrors.163.com/ubuntu/ wily-updates main restricted universe multiverse deb 
http://mirrors.163.com/ubuntu/ wily-proposed main restricted universe multiverse deb
 http://mirrors.163.com/ubuntu/ wily-backports main restricted universe multiverse deb-src 
http://mirrors.163.com/ubuntu/ wily main restricted universe multiverse deb-src 
http://mirrors.163.com/ubuntu/ wily-security main restricted universe multiverse deb-src
 http://mirrors.163.com/ubuntu/ wily-updates main restricted universe multiverse deb-src
 http://mirrors.163.com/ubuntu/ wily-proposed main restricted universe multiverse deb-src
 http://mirrors.163.com/ubuntu/ wily-backports main restricted universe multiverse
```

- - 更新系统软件源
    apt-get update apt-get upgrade

  - 在更新的时候可能会出现失败

  - - 问题一:Temporary failure in name resolution
      \#无法解析,需要在
      vim /etc/resolv.conf
      \#添加内容
      nameserver 114.114.114.114
      nameserver 8.8.8.8
      \#再执行
      apt-get update
      ​

    - 查看ip命令不能用
      \#安装ifconfig
      sudo apt-get install net-tools


      总结:到这里,在win10子系统里安装ubuntu系统,基本就可以玩耍了,但是这
      个ubuntu是个简单版,里面有些软件可能没有,需要自己安装!



[解决GitHub下载速度太慢问题的方法汇总（持续更新，建议收藏）_一名机电研究生的博客-CSDN博客](https://blog.csdn.net/a2360051431/article/details/130857622)

修改了hosts文件之后，
用sudo /etc/init.d/networking restart 但是这个是暴力重启网络来刷新了dns。
可以用sudo /etc/init.d/nscd restart
如果报错没有这个文件，就通过sudo apt-get install nscd 安装。



常用命令

- 显示信息：wslfetch
- sudo vim /etc/hosts 修改host文件

- curl cip.cc 查看ip详细信息
- hostname -I  使用hostname命令获取主机名和IP地址
- ifconfig和ip addr show



wsl是win的代理：[为 WSL2 一键设置代理 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/153124468)

```
#!/bin/zsh
host_ip=$(cat /etc/resolv.conf |grep "nameserver" |cut -f 2 -d " ")
export ALL_PROXY="http://$host_ip:7890"
```

win传送文件到wsl:[将Windows系统中文件传入WSL子系统中_wsl文件传输_Bio大恐龙的博客-CSDN博客](https://blog.csdn.net/ouyangk1026/article/details/125300749)

cd /mnt转到 /mnt 目录下，你可以看到自己的盘信息。


找到你想转到wsl子系统下的文件。例如我想将下载的blast文件转到子系统下。我需要的文件在以下路劲下
/mnt/c/Users/86184/Downloads

选择复制或者移动你的文件到指定目录下，可以使用cp也可以使用mv，这里使用的是mv。

```
mv /mnt/c/Users/86184/Downloads/ncbi-blast-2.13.0+-x64-arm-linux.tar.gz /home/bio_kang/software/
```

下载powerlevel10k字体

官网：[nerd-fonts](https://github.com/ryanoasis/nerd-fonts)

[wsl使用zsh与终端美化 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/166103184)】

Powerlevel10k 作者推荐使用 [Meslo Nerd Font](https://link.zhihu.com/?target=https%3A//github.com/romkatv/powerlevel10k%23meslo-nerd-font-patched-for-powerlevel10k) 字体，Download these four ttf files:

- [MesloLGS NF Regular.ttf](https://link.zhihu.com/?target=https%3A//github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
- [MesloLGS NF Bold.ttf](https://link.zhihu.com/?target=https%3A//github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
- [MesloLGS NF Italic.ttf](https://link.zhihu.com/?target=https%3A//github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
- [MesloLGS NF Bold Italic.ttf](https://link.zhihu.com/?target=https%3A//github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

```
#全部下载
git clone https://github.com/ryanoasis/nerd-fonts.git --depth 1
cd nerd-fonts
./install.sh
```

[ubuntu 字体安装 —— 以nerd font为例_ubuntu nerdfont_HZ_Samuel的博客-CSDN博客](https://blog.csdn.net/qq_39785418/article/details/122796861)

[ubuntu 字体安装 —— 以nerd font为例 - 骏腾 - 博客园 (cnblogs.com)](https://www.cnblogs.com/zi-wang/p/12566898.html)

https://www.cnblogs.com/hongdada/p/14031915.html



安装exa(目录美化)： [Ubuntu安装exa_上衫_的博客-CSDN博客](https://blog.csdn.net/weixin_45908225/article/details/117598781)

lsd和exa：https://www.51cto.com/article/716286.html

lsd官网：[lsd-rs/lsd: The next gen ls command (github.com)](https://github.com/lsd-rs/lsd)

lsd安装使用：1.下载lsd的lsd-musl_1.0.0_amd64.deb文件，按自己电脑下载

							2. 终端执行sudo dpkg -i lsd-musl_1.0.0_amd64.deb
							2. 配置：[带图标显示的ls---lsd_ITKEY_的博客-CSDN博客](https://blog.csdn.net/lxyoucan/article/details/120152535)

vim的使用：[精通 VIM ，此文就够了 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/68111471)