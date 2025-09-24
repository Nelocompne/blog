---
title: Btrfs文件系统
date: 2024-08-21 17:41:32
tags:
- windows
- btrfs
categories:
- software
---

# 介绍

Btrfs文件系统，与甲骨文早期开发的文件系统，Linux常见但是windows还未实装。针对支持SSD的优化，体验用起来也非常好。如果想在windows上使用它你可以通过以下github地址获取一个windows驱动版本，它不仅仅支持磁盘访问，还支持设置btrfs的诸多特性。
<!-- more -->
**说明**：maharmstone/btrfs 在安装《原神》或类似软件的情况，存储出错： https://github.com/maharmstone/btrfs/issues/324 https://github.com/maharmstone/btrfs/issues/416 详细解释changelog https://github.com/maharmstone/btrfs/tree/v1.7.7

## 使用说明

如果是在linux操作系统下格式化的btrfs分区，到windows操作系统下会出现即使分配了盘符也不会在磁盘管理器中出现。

![非windows下格式化的分区](https://drive.ljzd.link/api/raw/?path=/Images/blog/QQ20241219-000850.png&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true)

win Btrfs驱动下有携带默认的格式化工具`mkbtrfs.exe`，先将需要格式化的分区格式化成windows常用的文件系统并分配盘符。然后`mkbtrfs [盘符号]`，例如： `mkbtrfs d` 就是将D盘格式化成btrfs格式。

![windows下格式化的分区](https://drive.ljzd.link/api/raw/?path=/Images/blog/QQ20241219-000923.png&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true)


## 软件logo

![logo](https://drive.ljzd.link/api/raw/?path=/Images/blog/t0198eafb93bfc8bb83.png&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true)

# 地址
| 官网      | Description |
| ----------- | ----------- |
| GITHUB      | https://github.com/maharmstone/btrfs |
