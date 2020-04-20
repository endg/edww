---
title: "F70AR"
description: 'F70AR光纤放大器的调节和设定'
keywords: ["光纤放大器", "F70AR"]
date: 2020-01-01T13:16:48-08:00
lastmod: 2020-03-01T13:16:48-08:00
draft: false
tags: ["equipment"]
categories: ["Work"]
author: "dan"
slug: 'f70ar'

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
# comment: false
# toc: false

# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
#contentCopyright: '<a href="https://github.com/gohugoio/hugoBasicExample" rel="noopener" target="_blank">See origin</a>'
reward: false
# mathjax: false
---
关键词：光纤放大器

## F70AR光纤放大器的调节和设定 

## 0x00 原理

先介绍反射式光纤和对照式光纤的工件原理: 

反射式光纤:内有两根管子,一根为发射管1,另一根为接受管2,当1发出的光线遇到被测物后.光线就会被反回来被2接受,在光纤放大器上形成一个信号.如H142上面的003和012 

对照式光纤:同样有一根发射管和一根接受管,但管1和管2的位置是相对的.管1发出的光线遇到被测物后,光线就被挡住无法被管2接受,此时就会在光纤放大器上形成一个信号.如食人鱼上就会用到;

## 1x00 调节

F70AR属于反射式光纤,调节方法如下: 

### 1x10 选择工作模式

 F70AR有两种显示模式:L和D两种模式. 

L模式:入光ON.一般使用反射式光纤时选择L模式.H160上使用此模式. 

D模式:遮光ON.一般对照式光纤时选择D模式. 

F:为检知延迟时间.表示光纤放大器延迟时间40ms再检测被测物.一般不必设定. 

模式选择调整方式:按住RUN键约3秒钟,进入模式选择.按RUN键可对L\D\F进行选择.按切换投光频率1及投光频率2,设定不同的投光周期可防止F70AR之间的相互干扰. 

### 1x20 设定F70AR光纤放大器的灵敏度

**手动设定法**: 

1. 开关由RUN位置推到SET位置,进入设定状态; 
2. 被测物位于欲设定位置时,按一下SET键; 
3. 被测物移开后,按一下SET键完成设定: 
4. 最后将开关由SET位置推回RUN位置完成锁定, 

**自动设定法:** 

1. 开关由RUN位置推到SET位置,进入设定状态; 
2. 按住SET键约3秒钟后进入自动判断模式.此时灯会从快速闪烁变成1秒钟一次; 
3. 继续按住SET键不放,让被测物在光纤前经过,重复3~8次; 
4. 被测物离开光纤检测区域后,放开SET键,灵敏度设定OK; 
5. 最后将开关由SET位置推回RUN.进入锁定状态. 

### 1x30 微调

最后我们还可以根据实际情况对F70AR进行微调. 

微调步骤如下: 

1. 将开关由RUN位置推到SET位置后马上再由SET位置推到RUN位置,进入手动微调状态; 
2. 此时F70AR光纤上的S会不停的闪烁; 
3. 此时就可以通过RUN键和SET键来加减设定值; 
4. 停止操作10秒后,自动完成锁定状态.  