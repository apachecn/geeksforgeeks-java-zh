# Java 中的 Month getLong()方法

> 原文:[https://www.geeksforgeeks.org/month-getlong-method-in-java/](https://www.geeksforgeeks.org/month-getlong-method-in-java/)

**getLong()** 方法是 Month ENUM 的内置方法，用于从这个月实例中获取指定时态字段的值作为 Long。

**语法** :

```
public long getLong(TemporalField field)

```

**参数**:此方法接受单个参数*字段*，其长表示将从本月实例返回。

**返回值**:该方法将指定字段的值作为长整型返回。

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

        // Get the value of field
        System.out.println(month.getLong(ChronoField.MONTH_OF_YEAR));
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

        // Get the value of field
        System.out.println(month.getLong(ChronoField.MONTH_OF_YEAR));
    }
}
```

**输出:**

```
12

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/time/month . html # getLong-Java . time . temporal field-](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#getLong-java.time.temporal.TemporalField-)