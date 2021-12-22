# Java 中的 ChronoLocalDate isBefore()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-is before-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-isbefore-method-in-java-with-examples/)

Java 中**chronolocalydate**接口的 **isBefore()** 方法检查该日期是否在指定日期之前，并返回一个表示该日期的布尔值。

**语法** :

```
public boolean isAfter(ChronoLocalDate date2)

```

**参数**:该方法接受单个强制参数*日期 2* 其他日期进行比较，不为空。

**返回值**:如果该日期在指定日期之前，则函数返回真。

下面的程序说明了 Java 中的 **isBefore()** 方法:

**程序 1** :

```
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-27");

        // Parses the second date
        ChronoLocalDate dt2
            = LocalDate.parse("2017-11-27");

        // Check if the specified date
        // is before this date
        System.out.println(dt1.isBefore(dt2));
    }
}
```

**输出:**

```
false

```

**程序二** :

```
// Program to illustrate the isBefore() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-27");

        // Parses the second date
        ChronoLocalDate dt2
            = LocalDate.parse("2019-11-27");

        // Check if the specified date
        // is before this date
        System.out.println(dt1.isBefore(dt2));
    }
}
```

**输出:**

```
true

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chroncaldate . html # is efore-Java . time . chroncaldate-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#isBefore-java.time.chrono.ChronoLocalDate-)