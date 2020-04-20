---
title: "使用HUGO更新网站"
description: '流程是复杂的就是因为不会写代码'
keywords: ["更新", "update"]
date: 2020-02-18T16:01:23+08:00
lastmod: 2020-02-18T16:01:23+08:00
draft: false
tags: ["hugo"]
categories: ["Web"]
author: "dan"
slug: 'hugo_write'
# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
# comment: false
# toc: false

# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
#contentCopyright: '<a href="https://github.com/gohugoio/hugoBasicExample" rel="noopener" target="_blank">See origin</a>'
reward: false
# mathjax: true
---
关键词：更新网站

使用HUGO更新网站

我使用HUGO更新网站，流程是复杂的，就是因为不会写代码，所以很麻烦，如果有好心人介绍一些简单的方法，那会万分感谢了。

1. 打开GITHUB桌面版

2. 点开REPOSITORY的show in explorer

3. 进入content文件夹，并进入你要写文章的文件夹

4. 复制一篇文章

5. 使用Typora打开该文件，进行编辑，保存

6. 回到网站根目录，SHIFT+右键，在此处打开powershell

7. 输入命令：hugo,生成网站

8. 打开winscp，

9. 登录虚拟主机的FTP，进入网站根目录

10. 窗口左侧选择对应到刚生成网站的public文件夹

11. 点击winscp软件的左上角的"同步",注意方向目标目录选择“远程”

12. 虚拟主机文件同步完毕，[小登纪]（http://www.964813.xyz）网站进行了更新

13. 回到github桌面版

14. 点击左下角的Commit to master，对编辑完的文件提交Commit

15. 点击github软件的右侧中间的"Push origin",推送到github网站作为备份

    作为结尾，我的编辑文章的流程实在太费事了，希望好朋友们给介绍一些方便的法子，

    **联系Email：lmg_bit（圈a）163.com** 

    [求助：为什么邮箱下划线在markdown中就识别错误呢]