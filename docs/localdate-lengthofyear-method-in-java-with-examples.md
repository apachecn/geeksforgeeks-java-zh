# Java 中的 LocalDate lengthOfYear()方法，示例

> 原文:[https://www . geesforgeks . org/local date-length of year-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-lengthofyear-method-in-java-with-examples/)

Java 中 LocalDate 类的 lengthOfYear()方法返回由该日期表示的年份长度。

**语法** :

```
public int lengthOfYear()

```

**参数**:此方法不接受参数。

**返回值**:如果年份是闰年，函数返回 366，否则返回 365。

下面的程序说明了 Java 中 LocalDate 的 **lengthOfYear()** 方法:

**程序 1** :

```
// Program to illustrate the lengthOfYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        LocalDate dt1 = LocalDate.parse("2018-11-27");

        // Checks
        System.out.println(dt1.lengthOfYear());
    }
}
```

**输出:**

```
365

```

**程序二** :

```
// Program to illustrate the lengthOfYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the first date
        LocalDate dt1 = LocalDate.parse("2016-11-27");

        // Checks
        System.out.println(dt1.lengthOfYear());
    }
}
```

**输出:**

```
366

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # length of year()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#lengthOfYear())