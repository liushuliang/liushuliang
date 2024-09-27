---
title: Windows命令：type
author: 刘公子
categories: 工具技巧
date: 2024-09-26 16:32:00
---
## 语法格式

type命令显示文本文件的内容，类似Linux的`cat`

```sh
type [drive:][path]filename
```

## 显示内容

主要用于显示`ASCII`编码文件，其他编码会乱的。

## 文件拼接

`type *.sql >> a.sql`