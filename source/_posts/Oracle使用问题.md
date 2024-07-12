---
title: Oracle使用问题
date: 2024-07-05 09:54:20
tags: Oracle
categories: 数据库
---
# Oracle——记一次使用问题

Oracle用户创建之后需要赋予其连接数据库的能力：

```sql
GRANT CREATE SESSION TO <username>;
```

在Oracle数据库中，一个模式（Schema）通常对应一个数据库用户。具体来说，模式就是一个数据库用户的集合名空间，包含该用户拥有的所有数据库对象，如表、视图、索引、存储过程等。

所以在Spring等配置数据库是需要使用特定用户连接特定的Schema。