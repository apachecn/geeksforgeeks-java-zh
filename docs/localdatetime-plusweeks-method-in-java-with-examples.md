# Java 中的 LocalDateTime plusWeeks()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-plusweeks-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-plusweeks-method-in-java-with-examples/)

**LocalDateTime 类**的 **plusWeeks()** 方法用于返回添加了指定周的该日期时间的副本。

**语法**:

```java
public LocalDateTime plusWeeks(long weeks)
```

**参数**:接受单个参数**周数**，指定要添加的周数，可以是负数。

**返回值**:该方法根据添加了周的日期时间返回**本地日期时间**。

**异常**:程序抛出**日期时间异常**，如果结果超出支持的周数范围，则抛出该异常。

下面的程序说明了 Java 中的 LocalDateTime.plusWeeks()方法:

**程序 1** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the plusWeeks() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T10:15:30");

        System.out.println("LocalDateTime with 15 weeks added: "
                           + dt1.plusWeeks(15));
    }
}
```

**Output:** 

```java
LocalDateTime with 15 weeks added: 2018-04-26T10:15:30
```

**程序 2** :

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to illustrate the plusWeeks() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T08:15:30");

        System.out.println("LocalDateTime with -2 weeks added: "
                           + dt1.plusWeeks(-2));
    }
}
```

**Output:** 

```java
LocalDateTime with -2 weeks added: 2017-12-28T08:15:30
```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # plusWeeks(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#plusWeeks(long))