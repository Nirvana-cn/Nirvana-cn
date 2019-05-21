---
title: 如何配置环境变量
date: 2019-05-10 10:59:08
tags:
- environment-variables
categories:
- 少年,你渴望力量吗
---

学会如何配置环境变量啦😅😅😅。

<!--more-->

## 1. Windows配置

### 1.1 临时配置

直接在`cmd`环境配置即可，查看环境变量，添加环境变量，删除环境变量。

```bash
#node中常用的到的环境变量是NODE_ENV，首先查看是否存在 
set NODE_ENV 
#如果不存在则添加环境变量 
set NODE_ENV=production 
#环境变量追加值 set 变量名=%变量名%;变量内容 
set path=%path%;C:\web;C:\Tools 
#某些时候需要删除环境变量 
set NODE_ENV=
```

### 1.2 永久配置

右键(此电脑) -> 属性(R) -> 高级系统设置 -> 环境变量(N)...


## 2. Linux配置

### 2.1 临时配置

查看环境变量，添加环境变量，删除环境变量

```bash
#node中常用的到的环境变量是NODE_ENV，首先查看是否存在
echo $NODE_ENV
#如果不存在则添加环境变量
export NODE_ENV=production
#环境变量追加值
export path=$path:/home/download:/usr/local/
#某些时候需要删除环境变量
unset NODE_ENV
#某些时候需要显示所有的环境变量
env
```

### 2.2 永久配置

打开配置文件所在

```bash
# 所有用户都生效
vim /etc/profile
# 当前用户生效
vim ~/.bash_profile
```

在文件末尾添加类似如下语句进行环境变量的设置或修改

```bash
# 在文件末尾添加如下格式的环境变量
export path=$path:/home/download:/usr/local/
export NODE_ENV = product
```

最后修改完成后需要运行如下语句令系统重新加载

```bash
# 修改/etc/profile文件后
source /etc/profile
# 修改~/.bash_profile文件后
source ~/.bash_profile
```

## 3. 更多

Node环境变量那些事儿：[>>>点我进入](https://segmentfault.com/a/1190000011683741)