---
title: redmon实践
date: 2024-02-29
tags:
- windows
- redmon
- printer
categories:
- software
---

# 介绍
设计思路来源：[GhostScript实现镜像打印输出_操作系统_网上学园_科技时代_新浪网 (sina.com.cn)](https://tech.sina.com.cn/c/2001-09-10/5733.html)，[Ghostscript, Ghostview and GSview (wisc.edu)](https://pages.cs.wisc.edu/~ghost/)

<!-- more -->
## 准备：

- [Ghostscript : Downloads](https://ghostscript.com/releases/gsdnld.html)
- [Obtaining GSview 5.0 (ghostgum.com.au)](http://www.ghostgum.com.au/software/gsview.htm)
- [RedMon - Redirection Port Monitor (ghostgum.com.au)](http://www.ghostgum.com.au/software/redmon.htm)

## 设计思路：

![](https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/%E8%AE%BE%E8%AE%A1%E6%80%9D%E8%B7%AF-2024-02-29-2202_1709216457918_0.png&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true)
## redmon虚拟机打印设置

<video autoplay muted loop class="video">
    <source src="https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/redmon%E8%99%9A%E6%8B%9F%E6%89%93%E5%8D%B0%E6%9C%BA%E8%AE%BE%E7%BD%AE_1709214868699_0.mp4&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true" type="video/mp4">
    很抱歉，您的浏览器不支持 HTML5 原生视频。
</video>
安装后，添加本地打印机，创建新端口“Redirected Port”，端口名称（Port Name）默认，选择有镜像打印功能的打印机型号进行添加（例子使用了HP Color LaserJet 2800 Series PS）。

## 虚拟打印机默认设置修改

<video autoplay muted loop class="video">
    <source src="<video autoplay muted loop class="video">
    <source src="https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/%E8%99%9A%E6%8B%9F%E6%89%93%E5%8D%B0%E6%9C%BA%E9%BB%98%E8%AE%A4%E8%AE%BE%E7%BD%AE%E4%BF%AE%E6%94%B9_1709215141445_0.mp4&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true" type="video/mp4">
    很抱歉，您的浏览器不支持 HTML5 原生视频。
</video>
虚拟打印机默认设置，开启镜像打印功能。

![](https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/6_1709822322088_0.png&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true)

## 安装环境
<video autoplay muted loop class="video">
    <source src="<video autoplay muted loop class="video">
    <source src="https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/%E5%AE%89%E8%A3%85%E7%8E%AF%E5%A2%83_1709216647014_0.mp4&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true" type="video/mp4">
    很抱歉，您的浏览器不支持 HTML5 原生视频。
</video>

- 安装 **Ghostscript** 和 GSview 。
- 安装 **Ghostscript** 后确保 _“Generate cidfmap for Windws CJK TrueType fonts”_ 开启。

## 虚拟打印机配置输出参数1
<video autoplay muted loop class="video">
    <source src="<video autoplay muted loop class="video">
    <source src="https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/%E8%99%9A%E6%8B%9F%E6%89%93%E5%8D%B0%E6%9C%BA%E9%85%8D%E7%BD%AE%E8%BE%93%E5%87%BA%E5%8F%82%E6%95%B0_1709216790097_0.mp4&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true" type="video/mp4">
    很抱歉，您的浏览器不支持 HTML5 原生视频。
</video>

虚拟打印机端口配置中，重定向到 **GSview** 的`gsprint.exe`程序中。

## 虚拟打印机配置输出参数2

<video autoplay muted loop class="video">
    <source src="<video autoplay muted loop class="video">
    <source src="https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/%E8%99%9A%E6%8B%9F%E6%89%93%E5%8D%B0%E6%9C%BA%E9%85%8D%E7%BD%AE%E8%BE%93%E5%87%BA%E5%8F%82%E6%95%B02_1709216882345_0.mp4&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true" type="video/mp4">
    很抱歉，您的浏览器不支持 HTML5 原生视频。
</video>

配置`gsprint.exe`程序执行参数：
- `-noquery` 打印时不输出日志
- `-printer "name"` 指定实际打印机名称
- `-ghostscript "name"` 指定 **Ghostscript** 主程序路径
- 在所有参数最后 **单独** 添加一个`-`参数作为结尾。
- （可选）“Run” 运行方式 “Hidden” 隐藏。

![](https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/7_1709822353747_0.png&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true)

## 通过虚拟机打印

<video autoplay muted loop class="video">
    <source src="<video autoplay muted loop class="video">
    <source src="https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/%E9%80%9A%E8%BF%87%E8%99%9A%E6%8B%9F%E6%9C%BA%E6%89%93%E5%8D%B0_1709217192479_0.mp4&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true" type="video/mp4">
    很抱歉，您的浏览器不支持 HTML5 原生视频。
</video>
打印时选择“虚拟打印机”进行打印。

## redmon不支持windows10及以上的系统

![](https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/A_1709217250631_0.png&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true)

解决方法见 [[clawPDF实践]]