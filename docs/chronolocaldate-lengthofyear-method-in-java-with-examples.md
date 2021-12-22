# Java 中的 ChronoLocalDate lengthOfYear()方法，示例

> 原文:[https://www . geesforgeks . org/chronolocaldata-length of year-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-lengthofyear-method-in-java-with-examples/)

Java 中**ChronalDate**接口的 **lengthOfYear()** 方法返回该日期所代表的年份长度。

**语法** :

```java
public int lengthOfYear()

```

**参数**:此方法不接受参数。

**返回值**:如果年份是闰年，则函数返回 **366** ，否则返回 **365** 。

下面的程序说明了 Java 中的 **lengthOfYear()** 方法:

**程序 1** :

```java
// Program to illustrate the lengthOfYear() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-27");

        // Get the length of the year
        System.out.println(dt1.lengthOfYear());
    }
}
```

**输出:**

```java
365

```

**程序二** :

```java
// Program to illustrate the lengthOfYear() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDate dt1
            = LocalDate.parse("2016-11-27");

        // Get the length of the year
        System.out.println(dt1.lengthOfYear());
    }
}
```

**输出:**

```java
366

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldate . html # length of year–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#lengthOfYear--)