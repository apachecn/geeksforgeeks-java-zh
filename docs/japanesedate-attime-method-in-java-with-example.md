# Java 中的 JapaneseDate atTime()方法，示例

> 原文:[https://www . geesforgeks . org/japanesedate-at time-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesedate-attime-method-in-java-with-example/)

**Java . time . chrono . JapaneseDate**类的 **atTime()** 方法用于将这个 JapaneseDate 时间与一个本地时间相加，产生一个等价的日期和时间。

**语法:**

```
public final ChronoLocalDateTime
      atTime(LocalTime localTime)

```

**参数**:该方法以 LocalTime 类型的**对象为参数。
**返回值:**此方法通过将该日本日期与经过的当地时间相加，返回 Chrono 当地日期时间。**

以下是举例说明 **atTime()** 方法:
T3】例 1:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// atTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
              = JapaneseDate.now();

            // creating and initializing
            // TemporalAccessor object
            LocalTime localtime
              = LocalTime.now();

            // getting Chrono Local date time
            // by using atTime() method
            ChronoLocalDateTime<JapaneseDate> date
                = hidate.atTime(localtime);

            // display the result
            System.out.println(
              "Chrono LocalDateTime is: "
              + date);
        }
        catch (DateTimeException e) {
            System.out.println(
              "passed parameter can"
              + " not form a date");
            System.out.println(
              "Exception thrown: " + e);
        }
    }
}
```

**Output**

```
Chrono LocalDateTime is: Japanese Heisei 32-03-18T17:18:51.528

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// atTime() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
              = JapaneseDate.now();

            // creating and initializing
            // TemporalAccessor object
            LocalTime localtime
              = LocalTime.of(8, 20);

            // getting Chrono Local date time
            // by using atTime() method
            ChronoLocalDateTime<JapaneseDate> date
                = hidate.atTime(localtime);

            // display the result
            System.out.println(
              "Chrono LocalDateTime is: "
              + date);
        }
        catch (DateTimeException e) {
            System.out.println(
              "passed parameter can"
              + " not form a date");
            System.out.println(
              "Exception thrown: " + e);
        }
    }
}
```

**Output**

```
Chrono LocalDateTime is: Japanese Heisei 32-03-18T08:20

```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # atTime-Java . time . local time-T4】