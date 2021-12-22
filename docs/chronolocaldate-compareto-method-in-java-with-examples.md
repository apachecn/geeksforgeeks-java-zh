# Java 中的 ChronoLocalDate compareTo()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-compareto-method-in-java-with-examples/)

Java 方法中**ChronalDate**接口的 **compareTo()** 方法将此日期与另一个日期进行比较。

**语法** :

```
public int compareTo(ChronoLocalDate other)

```

**参数**:该方法接受一个参数*其他*，该参数指定要比较的其他日期，并且不是特别空。

**返回值**:它返回比较器值，比较器值小则为负，大则为正。

下面的程序说明了 Java 中的 ChronoLocalDate 的 compareTo()方法:

**程序 1** :

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoLocalDate dt
            = LocalDate.parse("2018-11-01");

        System.out.println(dt);

        // Second date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-14");

        System.out.println(dt1);

        // Compare both dates
        System.out.println(dt1.compareTo(dt));
    }
}
```

**输出:**

```
2018-11-01
2018-11-14
13

```

**程序二** :

```
// Program to illustrate the compareTo() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoLocalDate dt
            = LocalDate.parse("2018-11-21");
        System.out.println(dt);

        // Second date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-14");
        System.out.println(dt1);

        // Compare both dates
        System.out.println(dt1.compareTo(dt));
    }
}
```

**输出:**

```
2018-11-21
2018-11-14
-7

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chrolcaldate . html # share-Java . time . chrolcaldate-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#compareTo-java.time.chrono.ChronoLocalDate-)