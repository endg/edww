---
title: "安装完 Debian 10 后要做的事"
description: '安装基本满足必备的一些需求'
keywords: ["debian"]
date: 2020-02-06T13:16:48-08:00
lastmod: 2020-02-06T13:16:48-08:00
draft: false
tags: ["debian"]
categories: ["Web"]
author: "dan"
slug: 'debian_10after'

weight: 1

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
# comment: false
# toc: false

# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
#contentCopyright: '<a href="https://github.com/gohugoio/hugoBasicExample" rel="noopener" target="_blank">See origin</a>'
# reward: false
# mathjax: false
---
关键词：debian安装

Debian 10，代号「Buster」，包含了很多特色功能。如果你最近尝试在你的电脑上安装了 Debian 10，安装之后不知道下一步怎么做，本教程可以做为一个参考。

## 安装sudo

Debian 10 安装完成后，为了便于后续命令执行使用普通账号安装需要管理员权限才能安装的软件包，需要首先安装sudo软件包。

在root账号下，执行如下命令安装sudo。

```
apt install sudo -y
```

添加你的本地用户到 sudo 组，可以使用 usermod 命令，如下：

```
sudo usermod -aG sudo dan
```

## 清理不必要的软件包

目的：减少需要下载的内容从而缩短升级时间，降低出现依赖问题的可能性。

方法：先手动清除不必要的软件，然后参考我之前关于清理Debian/Ubuntu系统上冗余包的文章，删除掉冗余包、废弃包。简单来说就是执行下面两个命令，如果情况比较复杂（aptitude认为依赖关系复杂，无法稳妥地完全自行完成，提示用户是否要接受它计算出的一个解决方案），可以接受建议方案并再次执行直到没有包能被删除。

```
apt-get install aptitude
sudo aptitude purge "~o" -y
#dpkg —list |grep "rc" | cut -d " " -f 3 | xargs sudo dpkg —purge
sudo aptitude purge "~c" -y
```

## 升级当前系统中的软件包

```
sudo apt update
sudo apt upgrade
apt-get dist-upgrade
```

回答每一个可能出现的问题, 完成系统升级.

## 检查

强烈建议在升级对已经安装的包进行检查，并解决所有hold的包（卸载或上网查询具体方案）。

1.检查安装的包的一致性（正常情况下无输出）

```
dpkg -C
```

2.查看无法升级（on hold）的包（正常情况下无输出）

```
apt-mark showhold
```

## 重启

通常新版本会更使用新的内核，重启是为了使用新的内核image，同时方便删除旧的版本。

## 清理

### 清理作废的包。

升级后，很多旧版本的包将不再需要。除了apt-get autoremove可以删除的，还有一些需要使用更底层的dpkg工具进行删除。

```
sudo apt-get autoremove
sudo aptitude purge "~o"
#dpkg —list |grep "rc" | cut -d " " -f 3 | xargs sudo dpkg —purge
sudo aptitude purge "~c"
```

### 清理下载缓存

```
sudo apt-get clean
```

## 使用 TUNA 的软件源镜像[^使用 TUNA 的软件源镜像]

[^使用 TUNA 的软件源镜像]: 参考网址：[https://mirrors.tuna.tsinghua.edu.cn/help/debian/](https://mirrors.tuna.tsinghua.edu.cn/help/debian/)

- 选择你的 Debian 版本
- 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释 

```
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ buster main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ buster main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-updates main contrib non-free
#deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-updates main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-backports main contrib non-free
#deb-src https://mirrors.tuna.tsinghua.edu.cn/debian/ buster-backports main contrib non-free
deb https://mirrors.tuna.tsinghua.edu.cn/debian-security buster/updates main contrib non-free
# deb-src https://mirrors.tuna.tsinghua.edu.cn/debian-security buster/updates main contrib non-free
```

## 安装云音乐播放器

```
wget http://d1.music.126.net/dmusic/netease-cloud-music_1.2.1_amd64_ubuntu_20190428.deb 

sudo dpkg -i netease-cloud-music_1.2.1_amd64_ubuntu_20190428.deb 
```

若失败,修补依赖 sudo apt -f install,之后再安装

## 安装QQ

```
wget https://qd.myapp.com/myapp/qqteam/linuxQQ/linuxqq_2.0.0-b1-1024_amd64.deb
sudo dpkg -i linuxqq_2.0.0-b1-1024_amd64.deb
```

## 安装VLC播放器

VLC 是一款自由、开源的跨平台多媒体播放器及框架，可播放大多数多媒体文件，以及 DVD、音频 CD、VCD 及各类流媒体协议。

```
sudo apt install vlc -y
```