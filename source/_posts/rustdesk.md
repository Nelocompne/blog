---
title: Rustdesk
date: 2025-01-13
tags:
- windows
- server
categories:
- software
---

# 介绍

Rustdesk 快速使用参考。
<!-- more -->

该脚本快速重置rustdesk客户端。
并写入配置“停止自启服务”，“自建服务器地址写入（IP/域名）”，“key配置”，“支持LAN直连”。

```bat
@echo off
cd %appdata%
cd RustDesk
rd /s /q config
mkdir config && cd config
cls
pause

(
echo [options]
echo stop-service = 'Y'
echo custom-rendezvous-server = 'xxx.xxx.xxx.xxx'
echo key = 'xxxxxxxxxx'
echo direct-server = 'Y'
)>>RustDesk2.toml
cls
pause
```