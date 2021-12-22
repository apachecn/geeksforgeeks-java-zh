# Java 中的 LocalDate getMonth()方法

> 原文:[https://www . geesforgeks . org/local date-get month-method-in-Java/](https://www.geeksforgeeks.org/localdate-getmonth-method-in-java/)

Java 中 LocalDate 类的 getMonth()方法使用 Month 枚举获取年月字段。

**语法**:

```
public Month getMonth()

```

**参数**:该方法不接受任何参数。

**返回值**:函数返回一年中的月份。

下面的程序说明了 Java 中 LocalDate 的 **getMonth()** 方法:
**程序 1** :

```
// Program to illustrate the getMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getMonth());
    }
}
```

**Output:**

```
NOVEMBER

```

**程序 2** :

```
// Program to illustrate the getMonth() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-01-02");

        // Prints the day number
        System.out.println(dt.getMonth());
    }
}
```

**Output:**

```
JANUARY

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # getMonth()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getMonth())