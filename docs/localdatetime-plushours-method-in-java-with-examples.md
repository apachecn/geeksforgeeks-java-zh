# Java 中的 LocalDateTime plusHours()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-plushours-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-plushours-method-in-java-with-examples/)

**LocalDateTime 类**的 **plusHours()** 方法用于返回添加了指定小时的该日期时间的副本。

**语法** :

```
public LocalDateTime plusHours(long hours)

```

**参数**:接受单个参数**小时数**，指定要添加的小时数，可以是负数。

**返回值**:该方法根据添加了小时的日期时间返回**本地日期时间**。

**异常**:程序抛出**日期时间异常**，如果结果超过支持的小时范围，则抛出该异常。

下面的程序说明了 Java 中的 YearMonth.plusHours()方法:

**程序 1** :

```
// Program to illustrate the plusHours() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T10:15:30");

        System.out.println("LocalDateTime with 15 hours added: "
                           + dt1.plusHours(15));
    }
}
```

**输出:**

```
LocalDateTime with 15 hours added: 2018-01-12T01:15:30

```

**程序二** :

```
// Program to illustrate the plusHours() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T08:15:30");

        System.out.println("LocalDateTime with -2 hours added: "
                           + dt1.plusHours(-2));
    }
}
```

**输出:**

```
LocalDateTime with -2 hours added: 2018-01-11T06:15:30

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # plusHours(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#plusHours(long))