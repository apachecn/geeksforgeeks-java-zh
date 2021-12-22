# Java 中的 LocalDateTime getMonth()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-get month-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-getmonth-method-in-java-with-examples/)

**本地日期时间类**的 **getMonth()** 方法用于返回年月字段。此字段使用月份枚举返回。枚举可以提供基元 int 值。

**语法:**

```
public Month getMonth()

```

**参数:**此方法不接受任何参数。

**返回:**该方法返回该本地日期时间所在月份的**枚举月**。

下面的程序说明了 LocalDateTime.getMonth()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDateTime.getMonth() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2007-12-02T22:48:29");

        // get Month enum value field
        Month month = local.getMonth();

        // print result
        System.out.println("Month: "
                           + month);
    }
}
```

**输出:**

```
Month: DECEMBER

```

**程序二:**

```
// Java program to demonstrate
// LocalDateTime.getMonth() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2017-07-22T09:32:42");

        // get Month enum value field
        Month month = local.getMonth();

        // print result
        System.out.println("Month: "
                           + month);
    }
}
```

**输出:**

```
Month: JULY

```

参考:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # getMonth()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#getMonth())