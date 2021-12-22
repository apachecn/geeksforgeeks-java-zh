# Java 中的 ChronoLocalDate toString()方法，示例

> 原文:[https://www . geesforgeks . org/chronolocaldata-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-tostring-method-in-java-with-examples/)

一个**计时日期**界面的 **toString()** 方法是将这个日期作为字符串获取，比如 2019-01-01。输出将采用 ISO-8601 格式。

**语法:**

```
public String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回表示该日期的**字符串**，不为空。

下面的程序说明了 toString()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoLocalDate.toString() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate localD
            = LocalDate.parse("2018-12-06");

        // print ChronoLocalDate
        System.out.println("ChronoLocalDate: "
                           + localD.toString());
    }
}
```

**输出:**

```
ChronoLocalDate: 2018-12-06

```

**程序二:**

```
// Java program to demonstrate
// ChronoLocalDate.toString() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDate object
        ChronoLocalDate localD
            = LocalDate.parse("2021-06-30");

        // print ChronoLocalDate
        System.out.println("ChronoLocalDate: "
                           + localD.toString());
    }
}
```

**输出:**

```
ChronoLocalDate: 2021-06-30

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chroncaldate . html # tostring】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#toString--)