---
title: navicat重置脚本
date: 2024-07-10 16:35:49
tags: script
categories: 工具技巧
---

```sh
@echo off
 
reg delete "HKEY_CURRENT_USER\Software\PremiumSoft\NavicatPremium\Registration15XCS" /f
reg delete "HKEY_CURRENT_USER\Software\PremiumSoft\NavicatPremium\Update" /f
 
 
set regpath=HKEY_CURRENT_USER\Software\Classes\CLSID
 
 
 
set "str=HKEY_CURRENT_USER\Software\Classes\CLSID"
 
for /F "skip=1 tokens=1*" %%i in ('reg query "%str%" /s /k /f "info"') do (
 
reg delete "%%i" /F
 
)
pause
```

