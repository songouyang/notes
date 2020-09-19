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
cover: /data/thumbnails/40074.jpg
---

北邮 VPN 软件使用的是 GlobalProtect。在 macOS 操作系统上，GlobalProtect 程序不提供常规的退出选项，不仅安装启动后无法退出，而且开机自启动。借助 macOS 自带的服务管理工具 launchctl 不仅可以退出 GlobalProtect 程序，还可以选择关闭开机自启。

<!--more-->

GlobalProtect 的流氓之处在于：即使从活动监视器中强制杀进程，相关的进程也会立马重新自启动。常驻的进程不仅浪费系统资源，还有可能后台上传个人隐私。

## 退出

退出 GlobalProtect 程序，并不卸载软件。开机自启动任务仍然存在，所以下次开机仍会自动启动 GlobalProtect 程序。

```console
launchctl unload /Library/LaunchAgents/com.paloaltonetworks.gp.pangp*
```

如果不需要开机自启动，可以加上 w 参数去除开机自启。

```console
launchctl unload -w /Library/LaunchAgents/com.paloaltonetworks.gp.pangp*
```

## 启动

上面命令已经退出了 GlobalProtect 进程，如果需要再次启动，可以执行下面命令。

```console
launchctl load /Library/LaunchAgents/com.paloaltonetworks.gp.pangp*
```

同样的，如果需要打开开机自启选项，加上 w 参数即可。

```console
launchctl load -w /Library/LaunchAgents/com.paloaltonetworks.gp.pangp*
```

## 卸载

**方法一**
如果 GlobalProtect 的安装程序还存在，可以重新打开安装程序，取消勾选升级操作并且勾选卸载操作。
{% asset_img "Uninstall-GlobalProtect.png" '"使用安装程序卸载 GlobalProtect" "卸载 GlobalProtect"'%}

**方法二**
如果 GlobalProtect 的安装程序已经丢失，可以执行应用目录中的卸载脚本。

```console
sudo /Applications/GlobalProtect.app/Contents/Resources/uninstall_gp.sh
```
