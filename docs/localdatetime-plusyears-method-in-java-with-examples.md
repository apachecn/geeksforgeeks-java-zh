# Java 中的 LocalDateTime plusYears()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-plusyears-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-plusyears-method-in-java-with-examples/)

**LocalDateTime 类**的 **plusYears()** 方法用于返回添加了指定年份的该日期时间的副本。

**语法**:

```
public LocalDateTime plusYears(long years)
```

**参数**:接受单个参数**年份**，指定要添加的年份，可以是负数。

**返回值**:这个方法根据这个日期时间加上年份返回一个**本地日期时间**。

**异常**:程序抛出一个**日期时间异常**，如果结果超出支持的年份范围，则抛出该异常。

下面的程序说明了 Java 中的 LocalDateTime.plusYears()方法:

**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate the plusYears() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T10:15:30");

        System.out.println("LocalDateTime with 15 years added: "
                           + dt1.plusYears(15));
    }
}
```

**Output:** 

```
LocalDateTime with 15 years added: 2033-01-11T10:15:30
```

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate the plusYears() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T08:15:30");

        System.out.println("LocalDateTime with -2 years added: "
                           + dt1.plusYears(-2));
    }
}
```

**Output:** 

```
LocalDateTime with -2 years added: 2016-01-11T08:15:30
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # plusYears(long)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#plusYears(long))T4】