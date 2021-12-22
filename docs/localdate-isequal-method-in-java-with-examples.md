# Java 中的 LocalDate isEqual()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-isequal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-isequal-method-in-java-with-examples/)

Java 中 LocalDate 类的 isEqual()方法检查这个日期是否等于指定的日期。

**语法** :

```
public boolean isEqual(ChronoLocalDate date2)

```

**参数**:该方法接受单个强制参数*日期 2* 其他日期进行比较，不为空。

**返回值**:如果该日期等于指定日期，则函数返回真。

下面的程序说明了 Java 中 LocalDate 的 **isEqual()** 方法:

**程序 1** :

```
// Program to illustrate the isEqual() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        LocalDate dt1 = LocalDate.parse("2018-11-27");
        // Parses the second date
        LocalDate dt2 = LocalDate.parse("2018-11-27");

        // Checks
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

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        LocalDate dt1 = LocalDate.parse("2018-11-27");
        // Parses the second date
        LocalDate dt2 = LocalDate.parse("2015-11-27");

        // Checks
        System.out.println(dt1.isEqual(dt2));
    }
}
```

**输出:**

```
false

```

**参考**:[https://docs . Oracle . com/javae/10/docs/API/Java/time/local date . html # isequal(Java . time . cron . chrolcaldate)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isEqual(java.time.chrono.ChronoLocalDate))