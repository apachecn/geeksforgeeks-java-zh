# Java 中的 ChronoLocalDate from()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldearth-from-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-from-method-in-java-with-examples/)

Java 方法中**ChronalDate**接口的 **from()** 方法从时态对象中获取 ChronalDate 的一个实例。

**语法** :

```
public static ChronoLocalDate 
    from(TemporalAccessor temporal)

```

**参数**:该方法接受一个参数*时态*，指定要转换的时态对象，不为空。

**返回值**:返回时间位置日期，不为空。

**异常**:该函数只抛出*日期时间异常*，如果无法将其转换为时间位置日期，则会出现该异常。

下面的程序说明了 Java 中的 ChronoLocalDate 的 from()方法:

**注意**:每次运行输出都会改变。

```
// Program to illustrate the from() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {

        ChronoLocalDate dt
            = LocalDate.from(ZonedDateTime.now());

        System.out.println(dt);
    }
}
```

**输出:**

```
2019-04-28

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldeate . html # from-Java . time . temporal . temporal accessor-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#from-java.time.temporal.TemporalAccessor-)