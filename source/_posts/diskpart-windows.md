---
title: Windows自带命令行分区工具diskpart介绍
date: 2025-01-26
tags:
- windows
- 运维
categories:
- note
---

# 介绍

Diskpart是windows的命令行分区管理工具。

Windows命令行终端下执行 `DISKPART` 即可进入工具界面。在工具界面下通过输入 以help指令开头 `help <参数>` 查看对应参数介绍。
<!-- more -->

## 常见操作

1. 启动DiskPart
    - 打开命令提示符（按`Win + R`键，输入`cmd`，然后按Enter键）。
    - 在命令提示符中输入`diskpart`并按Enter键以启动DiskPart工具。
2. 列出磁盘和分区
    - 输入`list disk`以显示计算机上的所有磁盘。
    - 输入`list volume`以显示所有磁盘上的所有卷。
3. 选择对象
    - 输入`select disk n`来选择磁盘，其中n是磁盘的编号。
    - 输入`select volume n`来选择卷，其中n是卷的编号或驱动器号。
    - 输入`select partition n`来选择分区，其中n是分区的编号。
4. 创建分区
    - 输入`create partition primary size=n`来创建一个主分区，其中n是分区的大小（以MB为单位）。
    - 输入`create partition extended size=n`来创建一个扩展分区。
    - 输入`create partition logical size=n`来创建一个逻辑分区。
5. 删除分区
    - 输入`delete partition`来删除当前选中的分区。
6. 扩展分区
    - 输入`extend size=n`来扩展当前选中的分区，其中n是扩展的大小（以MB为单位）。
7. 格式化分区
    - 输入`format fs=ntfs label="Label Name" quick`来快速格式化当前选中的分区为NTFS文件系统，并赋予标签"Label Name"。
8. 分配驱动器号
    - 输入`assign letter=X`来为当前选中的卷分配驱动器号X，其中X是未使用的驱动器字母。
9. 清理磁盘
    - 输入`clean`来清除当前选中的磁盘上的所有分区和卷。
10. 转换磁盘类型
    - 输入`convert gpt`来将当前选中的磁盘转换为GPT分区样式。
    - 输入`convert mbr`来将当前选中的磁盘转换为MBR分区样式。
11. 设置分区为活动
    - 输入`active`来将当前选中的分区设置为活动分区。
12. 退出DiskPart
    - 输入`exit`来退出DiskPart工具。
在使用DiskPart时，请务必谨慎操作，因为错误的命令可能会导致数据丢失。在执行任何可能影响数据的操作之前，建议备份重要数据并确保您完全理解命令的作用。


## 小技巧

diskpart支持使用脚本运行，以此可以快速实现那些重复工作。

![编号对应的磁盘和卷](https://drive.ljzd.link/api/raw/?path=/Images/blog/diskpart1.jpg&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true)

示例：通过该脚本实现快速分配指定卷驱动号。

```bat
@echo off
(
echo select volume X // X更改为指定编号
echo assign letter=X // X更改为指定驱动号 
)>>script.txt
timeout /t 1
diskpart /s script.txt
timeout /t 1
del script.txt
pause
```

需要注意的是，每次对磁盘分区的操作后，都会导致磁盘或卷的编号顺序作出不同程度改变。

对此作出的可以修改脚本的方式：

```bat
@echo off
(
echo list volume
)>>list_volume.txt

timeout /t 1
diskpart /s list_volume.txt && del list_volume.txt

(
echo select volume X // 
echo assign letter=X //

)>>script.txt
notepad script.txt
pause

timeout /t 1
diskpart /s script.txt

timeout /t 1
del script.txt

pause
```
