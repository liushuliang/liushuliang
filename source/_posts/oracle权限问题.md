---
title: oracle权限问题
date: 2024-12-12 13:59:21
categories: 数据库
---

在修改oracle数据库表时报错：

​	```ORA-01031: insufficient privileges(权限不足)```

解决方法：

利用SYS执行`GRANT CREATE ANY TABLE TO YIXUAN`

![image-20241212143230000](./../images/image-20241212143230000.png)
