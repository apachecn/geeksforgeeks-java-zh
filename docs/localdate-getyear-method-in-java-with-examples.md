# Java 中的 LocalDate getYear()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-getyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-getyear-method-in-java-with-examples/)

Java 中 LocalDate 类的 getYear()方法获取 Year 字段。

**语法** :

```java
public int getYear()

```

**参数**:该方法不接受任何参数。

**返回值**:该函数返回年份，从 **MIN_YEAR** 到 **MAX_YEAR**

下面的程序说明了 Java 中 LocalDate 的 **getYear()** 方法:

**程序 1** :

```java
// Program to illustrate the getYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getYear());
    }
}
```

**输出:**

```java
2018

```

**程序二** :

```java
// Program to illustrate the getYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2015-11-27");

        // Prints the day number
        System.out.println(dt.getYear());
    }
}
```

**输出:**

```java
2015

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # getYear()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getYear())