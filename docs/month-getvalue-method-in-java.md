# Java 中的 Month getValue()方法

> 原文:[https://www . geesforgeks . org/month-getvalue-method-in-Java/](https://www.geeksforgeeks.org/month-getvalue-method-in-java/)

**getValue()** 方法是一个内置的 Month ENUM 方法，用于从这个 Month 实例中获取一年中某个月的值作为整数。

此方法返回的值在 1-12 的范围内，表示从 1 月到 12 月的月份。

**语法** :

```
public int getValue()

```

**参数**:该方法不接受任何参数。

**返回值**:该方法从本月实例中以整数形式返回年中月份的值。

下面的程序说明了上述方法:

**程序 1** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.MARCH;

        // Get the value of month-of-year as int
        System.out.println(month.getValue());
    }
}
```

**输出:**

```
3

```

**程序二** :

```
import java.time.*;
import java.time.Month;
import java.time.temporal.ChronoField;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.DECEMBER;

        // Get the value of month-of-year as int
        System.out.println(month.getValue());
    }
}
```

**输出:**

```
12

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # getValue–](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#getValue--)