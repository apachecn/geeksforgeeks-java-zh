# Java 中的 LocalDateTime plusSeconds()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-plus seconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-plusseconds-method-in-java-with-examples/)

**LocalDateTime 类**的 **plusSeconds()** 方法用于返回添加了指定秒的该日期时间的副本。

**语法**:

```java
public LocalDateTime plusSeconds(long seconds)
```

**参数**:接受单个参数**秒**，指定要添加的秒，可以是负数。

**返回值**:该方法根据添加了秒数的日期时间返回**本地日期时间**。

**异常**:程序抛出**日期时间异常**，如果结果超过支持的秒范围，则抛出该异常。

下面的程序说明了 Java 中的 LocalDateTime.plusSeconds()方法:

**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the plusSeconds() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T10:15:30");

        System.out.println("LocalDateTime with 15 seconds added: "
                           + dt1.plusSeconds(15));
    }
}
```

**Output:** 

```java
LocalDateTime with 15 seconds added: 2018-01-11T10:15:45
```

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the plusSeconds() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T08:15:30");

        System.out.println("LocalDateTime with -2 seconds added: "
                           + dt1.plusSeconds(-2));
    }
}
```

**Output:** 

```java
LocalDateTime with -2 seconds added: 2018-01-11T08:15:28
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # plus seconds(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#plusSeconds(long))