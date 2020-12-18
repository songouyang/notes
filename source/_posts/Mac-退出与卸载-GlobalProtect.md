---
title: Mac 退出与卸载 GlobalProtect
comments: true
mathjax: false
toc: false
tags:
  - VPN
  - macOS
categories: 软件技巧
abbrlink: 40074
date: 2020-03-07 13:40:32
---

北邮的校园 VPN 软件是 GlobalProtect。在 macOS 操作系统上，GlobalProtect 程序不提供常规的退出选项，不仅安装启动后无法退出，而且开机自启动。借助 macOS 自带的服务管理工具 launchctl 既可以退出 GlobalProtect 程序，也可以选择关闭程序开机自启。

<!--more-->

GlobalProtect 的流氓之处在于：即使从活动监视器中强制杀进程，相关的进程也会立马重新自启动。常驻的进程不仅浪费系统资源，还有可能后台上传个人隐私。打开系统自带的终端应用，输入下面的命令进行管理 GlobalProtect 程序。

## 退出

退出 GlobalProtect 程序，并不卸载软件。开机自启动任务仍然存在，所以下次开机时 GlobalProtect 程序会自启动。

```console
launchctl unload /Library/LaunchAgents/com.paloaltonetworks.gp.pangp*
```

如果不需要开机自启动，可以加上 w 参数去除开机自启。

```console
launchctl unload -w /Library/LaunchAgents/com.paloaltonetworks.gp.pangp*
```

## 启动

使用上面命令退出了 GlobalProtect 进程，如果需要再次启动，可以执行下面命令。

```console
launchctl load /Library/LaunchAgents/com.paloaltonetworks.gp.pangp*
```

同样的，如果需要开启自启动功能，加上 w 参数即可。

```console
launchctl load -w /Library/LaunchAgents/com.paloaltonetworks.gp.pangp*
```

## 卸载

**方法一**
假如 GlobalProtect 的安装程序还存在，可以重新打开安装程序，取消升级操作，并且勾选卸载操作。
{% img //sf6-ttcdn-tos.pstatp.com/obj/mosaic-legacy/137b000025fa7bad27111 '"使用安装程序卸载 GlobalProtect" "卸载 GlobalProtect"'%}

**方法二**
假如 GlobalProtect 的安装程序已经丢失，可以执行应用目录中的卸载脚本。如果提示需要密码，输入锁屏密码即可。

```console
sudo /Applications/GlobalProtect.app/Contents/Resources/uninstall_gp.sh
```
