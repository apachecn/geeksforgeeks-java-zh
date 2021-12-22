# Java 中的 chronolocaldeatIsrapyear()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-islapyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-isleapyear-method-in-java-with-examples/)

Java 中**ChronalDate**界面的**IsLapyear()**方法检查年份是否为闰年。

**语法** :

```
public boolean isLeapYear()

```

**参数**:此方法不接受参数。

**返回值**:如果年份是闰年，函数返回**真**，否则返回**假**。

下面的程序说明了 Java 中的**IsLappyear()**方法:

**程序 1** :

```
// Program to illustrate the isLeapYear() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        ChronoLocalDate dt1
            = LocalDate.parse("2018-11-27");

        // Checks
        System.out.println(dt1.isLeapYear());
    }
}
```

**输出:**

```
false

```

**程序二** :

```
// Program to illustrate the isLeapYear() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        ChronoLocalDate dt1
            = LocalDate.parse("2012-11-27");

        // Checks
        System.out.println(dt1.isLeapYear());
    }
}
```

**输出:**

```
true

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chroncaldate . html # iseappyear】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#isLeapYear--)