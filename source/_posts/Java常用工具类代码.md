---
title: Java常用工具类代码
date: 2024-07-23 17:20:49
categories: Java代码块
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

### equal比较

使用`("gcx_blood").equals(param.getObsvCode())`而不是`param.getObsvCode().equals()`

> 这样写可以避免空指针异常，如果`param.getObsvCode()`返回`null`。调用`equal()`会抛异常，而使用`("gcx_blood").equals(null)` 不会抛出异常，而是直接返回 `false`。
