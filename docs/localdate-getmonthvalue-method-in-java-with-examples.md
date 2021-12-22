# Java 中的 LocalDate getMonthValue()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-getmonthvvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-getmonthvalue-method-in-java-with-examples/)

Java 中 LocalDate 类的 getMonthValue()方法获取从 1 到 12 的年月字段。

**语法**:

```
public int getMonthValue()

```

**参数**:该方法不接受任何参数。

**返回值**:该函数以数字形式从 1-12 返回一年中的月份。

下面的程序说明了 Java 中 LocalDate 的**getmonthvvalue()**方法:
**程序 1** :

```
// Program to illustrate the getMonthValue() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getMonthValue());
    }
}
```

**Output:**

```
11

```

**程序 2** :

```
// Program to illustrate the getMonthValue() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-01-02");

        // Prints the day number
        System.out.println(dt.getMonthValue());
    }
}
```

**Output:**

```
1

```

**参考**:[https://docs . Oracle . com/javae/10/docs/API/Java/time/local date . html # getmonthvalue()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getMonthValue())