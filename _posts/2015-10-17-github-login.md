---
title: windows下，git设置默认的用户名密码
date: 2015-10-17 01:05:13 +0800
layout: post
permalink: /blog/2015/10/17/github-login.html
categories:
  - github
tags:
  - 生活
---
添加环境变量

1 在windows中添加一个HOME环境变量，变量名:HOME,变量值：E:\git

![](/images/env.png)

2 创建git用户名和密码存储文件

进入%HOME%目录，新建一个名为"_netrc"的文件，文件中内容格式如下：

machine github.com
login your-usernmae
password your-password

重新打开git bash即可，无需再输入用户名和密码