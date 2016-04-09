---
title: appium的安装
date: 2016-4-9 11:43:13 +0800
layout: post
permalink: /blog/2016/4/9/appiumInstall.html
categories:
  - app
tags:
  - app
---
sudo npm install -g appium,下载不下来，找了半天，发现淘宝有npm源http://npm.taobao.org/

然而淘宝也是坑，没下载下来，提示sha1不对。

最终在百度网盘上找到了最新的appium.dmg。

安装完成后，用appium-doctor检查环境。提示安卓home没有设置。

下载adt

建个文件，source一下，包括java环境变量内容如下：

export PATH=${PATH}:/Applications/adt-bundle-mac-x86_64-20140702/sdk/tools:/Applications/adt-bundle-mac-x86_64-20140702/sdk/platform-tools

export ANDROID_HOME="/Applications/adt-bundle-mac-x86_64-20140702/sdk"

export JAVA_HOME="/Library/Java/JavaVirtualMachines/jdk1.8.0_73.jdk/Contents/Home"

export PATH=$JAVA_HOME/bin:$PATH

export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar




