# Java 中的 ChronoLocalDate lengthOfMonth()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-length of month-in-Java-method-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-lengthofmonth-method-in-java-with-examples/)

Java 中**ChronalDate**接口的 **lengthOfMonth()** 方法返回该日期代表的月份长度。

**语法** :

```
public int lengthOfMonth()

```

**参数**:此方法不接受参数。

**返回值**:该函数以天为单位返回月的长度。

下面的程序说明了 Java 中的 **lengthOfMonth()** 方法:

**程序 1** :

```
// Program to illustrate the lengthOfMonth() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parse the date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-27");

        // Get the length of the month
        System.out.println(dt1.lengthOfMonth());
    }
}
```

**输出:**

```
30

```

**程序二** :

```
// Program to illustrate the lengthOfMonth() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-01-27");

        // Get the length of the month
        System.out.println(dt1.lengthOfMonth());
    }
}
```

**输出:**

```
31

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldeate . html # length of month–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#lengthOfMonth--)