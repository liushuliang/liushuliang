---
title: Java常用工具类代码
date: 2024-07-23 17:20:49
tags: Java代码块
---

## 常用方法

### `ObjectUtil.isEmpty()`

比较笼统的判断是否为空，不属于下面类型的仅仅判断是否为null

```java
    public static boolean isEmpty(Object obj) {
        if (null == obj) {
            return true;
        }

        if (obj instanceof CharSequence) {
            return StrUtil.isEmpty((CharSequence) obj);
        } else if (obj instanceof Map) {
            return MapUtil.isEmpty((Map) obj);
        } else if (obj instanceof Iterable) {
            return IterUtil.isEmpty((Iterable) obj);
        } else if (obj instanceof Iterator) {
            return IterUtil.isEmpty((Iterator) obj);
        } else if (ArrayUtil.isArray(obj)) {
            return ArrayUtil.isEmpty(obj);
        }

        return false;
    }
```

### `Optional.ofNullable().map().orElse()`

v指代是gms这个列表

```java 
List<AllErgenInfoResp> gms = wsAdpterService.getPatientGmInfo(hospitalNumber);
                patientTagVO.setIsGm(
                        Optional.ofNullable(gms)
                                .map(v -> !v.isEmpty())
                                .orElse(false)
                );
```

