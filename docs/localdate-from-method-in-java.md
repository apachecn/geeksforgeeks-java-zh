# Java 中 LocalDate from()方法

> 原文:[https://www . geesforgeks . org/local date-from-method-in-Java/](https://www.geeksforgeeks.org/localdate-from-method-in-java/)

Java 方法中 LocalDate 类的 from()方法从时态对象中获取 LocalDate 的一个实例。

**语法** :

```
public static LocalDate from(TemporalAccessor temporal)

```

**参数**:该方法接受一个参数*时态*，指定要转换的时态对象，不为空。

**返回值**:返回本地日期，不为空。

**异常**:该函数只抛出*日期时间异常*，如果无法将其转换为本地日期，则会出现该异常。

下面的程序说明了 Java 中 LocalDate 的 from()方法:

**注意**:每次运行输出都会改变。

```
// Program to illustrate the from() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        LocalDate dt = LocalDate.from(ZonedDateTime.now());
        System.out.println(dt);
    }
}
```

**输出:**

```
2018-11-28

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html #来自(Java . time . temporal . temporalacessor)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#from(java.time.temporal.TemporalAccessor))