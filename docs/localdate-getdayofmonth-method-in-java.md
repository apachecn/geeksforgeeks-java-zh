# Java 中的 LocalDate getDayOfMonth()方法

> 原文:[https://www . geesforgeks . org/local date-getdayofmonth-method-in-Java/](https://www.geeksforgeeks.org/localdate-getdayofmonth-method-in-java/)

Java 中 LocalDate 类的 getDayOfMonth()方法获取月中的某一天字段。

**语法** :

```java
public int getDayOfMonth()

```

**参数**:该方法不接受任何参数。

**返回值**:该函数返回 1-31 范围内的一个月中的某一天。

下面的程序说明了 Java 中 LocalDate 的 **getDayOfMonth()** 方法:

**程序 1** :

```java
// Program to illustrate the getDayOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        LocalDate dt = LocalDate.parse("2018-11-27");
        System.out.println(dt.getDayOfMonth());
    }
}
```

**输出:**

```java
27

```

**程序二** :

```java
// Program to illustrate the getDayOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        LocalDate dt = LocalDate.parse("2018-01-01");
        System.out.println(dt.getDayOfMonth());
    }
}
```

**输出:**

```java
1

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # getDayOfMonth()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getDayOfMonth())