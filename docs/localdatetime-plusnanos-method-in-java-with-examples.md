# Java 中的 LocalDateTime plusNanos()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-plusnanos-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-plusnanos-method-in-java-with-examples/)

**LocalDateTime 类**的 **plusNanos()** 方法用于返回添加了指定纳秒的该日期时间的副本。

**语法**:

```java
public LocalDateTime plusNanos(long nanoSeconds)
```

**参数**:接受单个参数**纳秒**，指定需要相加的纳秒，可以是负数。

**返回值**:该方法根据添加了纳秒的日期时间返回**本地日期时间**。

**异常**:程序抛出**日期时间异常**，如果结果超过支持的纳秒范围，则抛出该异常。

下面的程序说明了 Java 中的 LocalDateTime.plusNanos()方法:

**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the plusNanos() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T10:15:30");

        System.out.println("LocalDateTime with 10000 nanoSeconds added: "
                           + dt1.plusNanos(10000));
    }
}
```

**Output:** LocalDateTime with 10000 nanoSeconds added: 2018-01-11T10:15:30.000010  

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the plusNanos() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T08:15:30");

        System.out.println("LocalDateTime with -1500 nanoSeconds added: "
                           + dt1.plusNanos(-1500));
    }
}
```

**Output:** LocalDateTime with -1500 nanoSeconds added: 2018-01-11T08:15:29.999998500  

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # plusNanos(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#plusNanos(long))T4】