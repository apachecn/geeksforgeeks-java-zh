# Java 中的 MonthDay get()方法，示例

> 原文:[https://www . geesforgeks . org/monthday-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-get-method-in-java-with-examples/)

Java 中**月日类**的 **get()** 方法从这个月日获取指定字段的值作为 *int* 。

**语法:**

```
public int get(TemporalField field)
```

**参数:**该方法接受一个参数**字段**，指定要获取的字段，不为空。

**返回:**函数返回该字段的值。

**异常**:该函数抛出如下三个选项:

*   **[Date and Time Exception]** : It is thrown when the value of this field cannot be obtained or the value exceeds the valid value range of this field.
*   **Unsupported Temporaltypeexception** : thrown when the field is unsupported or the value range exceeds one int.
*   **Arithmetic exception** : thrown when numerical value overflows.

以下程序说明了 **MonthDay.get()** 方法:

**程序 1:**

```
// Program to illustrate the get() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        MonthDay tm1
            = MonthDay.parse("--10-12");

        System.out.println(
            tm1.get(ChronoField.DAY_OF_MONTH));
    }
}
```

**输出:**

```
12

```

**程序二:**

```
// Program to illustrate the get() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        MonthDay tm1
            = MonthDay.parse("--12-06");

        System.out.println(
            tm1.get(ChronoField.DAY_OF_MONTH));
    }
}
```

**输出:**

```
6

```

**程序 3:** 演示日期时间例外

```
// Program to illustrate the get() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {

        try {

            // Parses the date
            MonthDay tm1
                = MonthDay.parse("--13-12");

            System.out.println(
                tm1.get(ChronoField.DAY_OF_MONTH));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.time.format.DateTimeParseException:
 Text '--13-12' could not be parsed:
 Unable to obtain MonthDay from TemporalAccessor:
 {DayOfMonth=12, MonthOfYear=13},
 ISO of type java.time.format.Parsed

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/time/monthday . html # get-Java . time . temporal field-](https://docs.oracle.com/javase/8/docs/api/java/time/MonthDay.html#get-java.time.temporal.TemporalField-)