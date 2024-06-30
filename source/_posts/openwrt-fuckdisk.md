---
title: openwrt刷写固件之分区
date: 2024-06-30 11:53:01
tags:
- openwrt
categories:
- 笔记
---

# 介绍
分区，什么意思呢？对硬盘分区。
![openwrt-diskfun.jpg](https://s2.loli.net/2024/06/30/bDItMxZA61KUCcq.jpg)

<!-- more -->

# 开始

玩openwrt的人会遇到一些情况，写完固件发现默认分区不够大，扩容方法也有。
什么`overlay` 什么 `squashfs`，这里丢几个参考教程用于讨论研究：
- https://www.youtube.com/watch?v=YwbwzuXKNlg overlay
- https://www.izilzty.com/?post=5 squashfs

什么fdisk就一通操作下来基本上都能满足要求，用fdisk你甚至不用特地找个linux系统，装个msys2基本上就都能用了。我这边就根据 squashfs 相关的那篇文章来做个轻松版的。

Diskgenius大家应该都知道，直接用它的分区扩容，关键起始扇区号不动就行了。

![openwrt-diskfun2.jpg](https://s2.loli.net/2024/06/30/YWC9fOF5MtVmowk.jpg)

就这么简单。