# Java 中的 LocalDate lengthOfMonth()方法，示例

> 原文:[https://www . geesforgeks . org/local date-length of month-in-Java-method-with-examples/](https://www.geeksforgeeks.org/localdate-lengthofmonth-method-in-java-with-examples/)

Java 中 LocalDate 类的 lengthOfMonth()方法返回该日期表示的月份长度。

**语法** :

```java
public int lengthOfMonth()

```

**参数**:此方法不接受参数。

**返回值**:该函数以天为单位返回月的长度。

下面的程序说明了 Java 中 LocalDate 的 **lengthOfMonth()** 方法:

**程序 1** :

```java
// Program to illustrate the lengthOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        LocalDate dt1 = LocalDate.parse("2018-11-27");

        // Checks
        System.out.println(dt1.lengthOfMonth());
    }
}
```

**输出:**

```java
30

```

**程序二** :

```java
// Program to illustrate the lengthOfMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        LocalDate dt1 = LocalDate.parse("2018-01-27");

        // Checks
        System.out.println(dt1.lengthOfMonth());
    }
}
```

**输出:**

```java
31

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # length of month()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#lengthOfMonth())