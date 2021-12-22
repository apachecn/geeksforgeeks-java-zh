# Java 中的 ChronoLocalDate isEqual()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-isequal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-isequal-method-in-java-with-examples/)

Java 中**计时日期**界面的 **isEqual()** 方法检查该日期是否等于指定日期。

**语法** :

```
public boolean isEqual(ChronoLocalDate date2)

```

**参数**:该方法接受单个强制参数*日期 2* 其他日期进行比较，不为空。

**返回值**:如果该日期等于指定日期，则函数返回真。

下面的程序说明了 Java 中的 **isEqual()** 方法:

**程序 1** :

```
// Program to illustrate the isEqual() method

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
            = LocalDate.parse("2018-11-27");

        // Check if these two are equal
        System.out.println(dt1.isEqual(dt2));
    }
}
```

**输出:**

```
true

```

**程序二** :

```
// Program to illustrate the isEqual() method

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
            = LocalDate.parse("2015-11-27");

        // Check if these two are equal
        System.out.println(dt1.isEqual(dt2));
    }
}
```

**输出:**

```
false

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chrolcaldate . html # isequal-Java . time . chrolcaldate-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#isEqual-java.time.chrono.ChronoLocalDate-)