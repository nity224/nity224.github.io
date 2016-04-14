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


问题1。appium的ios的demo，运行的时候报错了，如下：

解决办法：iOS Settings——>Advanced,勾选Use Native Instruments Library

![](/images/ios.png)

｛info: [debug] And launch timeouts (in ms): {"global":90000}
info: [debug] [INST STDERR] dyld: could not load inserted library '/Applications/Appium.app/Contents/Resources/node_modules/appium/submodules/appium-instruments/thirdparty/iwd7/InstrumentsShim.dylib' because no suitable image found.  Did find:
	/Applications/Appium.app/Contents/Resources/node_modules/appium/submodules/appium-instruments/thirdparty/iwd7/InstrumentsShim.dylib: mmap() error 1 at address=0x10DAFD000, size=0x00001000 segment=__TEXT in Segment::map() mapping /Applications/Appium.app/Contents/Resources/node_modules/appium/submodules/appium-instruments/thirdparty/iwd7/InstrumentsShim.dylib

info: [debug] [INSTSERVER] Instruments exited with code null
info: [debug] Killall instruments
info: [debug] Instruments crashed on startup
info: [debug] Attempting to retry launching instruments, this is retry #3
info: [debug] Killall iOS Simulator
｝
