---
title: Windows7系统
date: 2024-05-29 00:27:41
tags:
- win7
- windows
categories:
- 系统
---

# 介绍
Windows7目前微软已经停止了有关它的一切更新，接下来会介绍一些相关的细节。
<!-- more -->
## SP1
如果你的win7没有获得SP1，除了安装带SP1版的win7系统，你还可以通过更新包来升级你的win7系统： 转到 Microsoft 网站上的 [Windows 7 Service Pack 1 下载页面](https://www.catalog.update.microsoft.com/Search.aspx?q=KB976932) 。[来源](https://support.microsoft.com/zh-cn/windows/%E5%AE%89%E8%A3%85-windows-7-service-pack-1-sp1-b3da2c0f-cdb6-0572-8596-bab972897f61)。
注意：里面包含x32位和x64位。升级包的大小为：32位	541.9 MB，64位	912.4 MB。

## SHA-2代码签名补丁
即使你已经是通过SP1版win7官方镜像安装的，你会遇到“SHA-2代码签名”补丁缺失导致的如“火绒”不能安装。
如果要打上该补丁，你可以选择两种方案：
1. 火绒官方的 “火绒安全-SHA-2代码签名补丁修复工具”，[下载](https://down5.huorong.cn/tools/sha256_fix.exe)。
2. 微软官网下载补丁： [KB4474419](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4474419)、
[KB4490628](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4490628)

## .net 4
在未升级SP1版本的win7系统下，你将无法安装.net4或者更高的版本。并且你将无法通过Cleanflash（已知版本：v34.0.0.308 ）补丁Flash，因为它至少依赖.net4。

但即使你已经获得SP1，但是仍有可能无法安装.net4.8并得到“未授权签名”相关的原因无法安装，你将有两种解决方法，一是通过BypassESU，二是直接解压安装包进行安装。

## UpdatePack7


**说明**：

## 软件截图

![]()

# 地址
| 官网      | Description |
| ----------- | ----------- |
| GITHUB      | Title       |
| FOSSHUB     | Text        |
| sourceforge | Text        |
