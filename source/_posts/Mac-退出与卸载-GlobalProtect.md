---
title: Mac 退出与卸载 GlobalProtect
comments: true
mathjax: false
toc: false
tags:
  - VPN
  - Mac
categories: 软件技巧
abbrlink: 40074
date: 2020-03-07 13:40:32
thumbnail:
---

北邮的校园 VPN 软件是 GlobalProtect。GlobalProtect 程序不提供退出的选项，一旦安装启动后，便无法退出，而且开机自启动。即使从活动监视器中强制退出进程，GlobalProtect 进程也会重新自启动。
常驻的进程不仅浪费系统资源，还有可能后台上传个人隐私。既然不能使用常规的退出方式，那么可以使用 Mac 中的服务管理工具退出 GlobalProtect。

<!--more-->

## 退出

只是退出进程和关闭软件自启动，并不卸载软件。方便下次使用的时候快速启动。

```console
$ launchctl unload /Library/LaunchAgents/com.paloaltonetworks.gp.pangp*
```

## 启动

上面已经退出了 GlobalProtect 进程，如果需要再次启动，可以执行下面命令。

```console
$ launchctl load /Library/LaunchAgents/com.paloaltonetworks.gp.pangp*
```

## 卸载

**方法一**
如果 GlobalProtect 的安装程序还存在，可以重新打开安装程序，取消勾选升级操作并且勾选卸载操作。
{% asset_img "Uninstall-GlobalProtect.png" "Uninstall GlobalProtect" %}

**方法二**
如果 GlobalProtect 的安装程序已经丢失，可以执行应用目录中的卸载脚本。

```console
$ sudo /Applications/GlobalProtect.app/Contents/Resources/uninstall_gp.sh
```
