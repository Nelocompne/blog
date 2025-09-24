---
title: 虚拟PDF打印机clawPDF实践
date: 2024-03-07
tags:
- windows
- printer
- Ghostscript
categories:
- software
---

## 准备

- [clawsoftware/clawPDF: Open Source Virtual (Network) Printer for Windows that allows you to create PDFs, OCR text, and print images, with advanced features usually available only in enterprise solutions. (github.com)](https://github.com/clawsoftware/clawPDF)

<!-- more -->
## 安装clawPDF
<video autoplay muted loop class="video">
    <source src="https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/%E5%AE%89%E8%A3%85clawPDF_1709822469353_0.mp4&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true" type="video/mp4">
    很抱歉，您的浏览器不支持 HTML5 原生视频。
</video>

## clawPDF虚拟打印机配置设置
<video autoplay muted loop class="video">
    <source src="https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/clawPDF%E8%99%9A%E6%8B%9F%E6%89%93%E5%8D%B0%E6%9C%BA%E9%85%8D%E7%BD%AE%E8%AE%BE%E7%BD%AE_1709822484400_0.mp4&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true" type="video/mp4">
    很抱歉，您的浏览器不支持 HTML5 原生视频。
</video>

打开“clawPDF”虚拟打印机选项设置，“高级”，“文档选项”-“PostScript选项”-“镜像输出：是”。

## clawPDF配置及打印
<video autoplay muted loop class="video">
    <source src="https://drive.ljzd.link/api/raw/?path=/Images/blog/jkfl/clawPDF%E9%85%8D%E7%BD%AE%E5%8F%8A%E6%89%93%E5%8D%B0_1709822491978_0.mp4&odpt=f68a9f95c330098a55256b6d2d21ff1901798a4b6b132b3ab94d33c0ba017543&proxy=true" type="video/mp4">
    很抱歉，您的浏览器不支持 HTML5 原生视频。
</video>

开始菜单找到“clawPDF”，“文件参数设置”：
- 保存：转换后使用标准查看器打开，关闭，在批处理任务下避免重复打开。
- 自动保存：启用自动保存，开启，在批处理任务下避免手动保存。
- 动作：打印文件，开启，将输出的处理自动跳转到打印流程。

打印时，选择“clawPDF”虚拟打印机进行打印，之后再从打印机选项中选择实际打印机打印。

优点：Windows多版本集成，开源，集成GhostScript。
缺点：打印处理本质为将输出的PDF文件进行打印，如文档内容复杂度高，面对性能较慢的机器需要花费更多时间。

## 常见问题

如遇到无法安装clawPDF，请安装微软vc++运行库后重试。