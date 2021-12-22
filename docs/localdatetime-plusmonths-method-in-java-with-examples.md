# Java 中的 LocalDateTime plusMonths()方法，示例

> 原文:[https://www . geesforgeks . org/local datetime-plusmonths-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-plusmonths-method-in-java-with-examples/)

**LocalDateTime 类**的 **plusMonths()** 方法用于返回添加了指定月份的该日期时间的副本。

**语法** :

```
public LocalDateTime plusMonths(long months)

```

**参数**:接受单个参数**月份**，指定要添加的月份，可以是负数。

**返回值**:该方法根据添加了月份的日期时间返回**本地日期时间**。

**异常**:程序抛出**日期时间异常**，如果结果超出支持的月份范围，则抛出该异常。

下面的程序说明了 Java 中的 YearMonth.plusMonths()方法:

**程序 1** :

```
// Program to illustrate the plusMonths() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T10:15:30");

        System.out.println("LocalDateTime with 15 months added: "
                           + dt1.plusMonths(15));
    }
}
```

**输出:**

```
LocalDateTime with 15 months added: 2019-04-11T10:15:30

```

**程序二** :

```
// Program to illustrate the plusMonths() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        LocalDateTime dt1
            = LocalDateTime
                  .parse("2018-01-11T08:15:30");

        System.out.println("LocalDateTime with -2 months added: "
                           + dt1.plusMonths(-2));
    }
}
```

**输出:**

```
LocalDateTime with -2 months added: 2017-11-11T08:15:30

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # plusMonths(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#plusMonths(long))