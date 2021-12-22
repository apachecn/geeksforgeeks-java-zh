# Java 中的 ChronoLocalDate adjustInto()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-adjustin to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-adjustinto-method-in-java-with-examples/)

Java 中**ChronalDate**界面的**adjustitinto()**方法用于调整指定的时态对象，使其与该对象具有相同的日期。

**语法** :

```
public Temporal adjustInto(Temporal temporal)

```

**参数**:该方法接受单个参数*时间*，该参数为需要调整的目标对象，不具体为空。

**返回值**:返回调整后的对象，不为空。

**异常**:函数抛出如下所述的两个异常:

1.  **[datetimeexception]** : thrown when the program cannot be adjusted.
2.  **Arithmetic exception** : If there is a numerical overflow, the program will throw this.

下面的程序说明了 Java 中的 ChronoLocalDate 的 adjustInto()方法:

**程序 1** :

```
// Program to illustrate the adjustInto() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {

        ZonedDateTime date
            = ZonedDateTime.now();

        // prints the date
        System.out.println(date);

        // Parses the date
        ChronoLocalDate date1
            = LocalDate.parse("2015-01-31");

        // Uses the function to adjust the date
        date = (ZonedDateTime)date1.adjustInto(date);

        // Prints the adjusted date
        System.out.println(date);
    }
}
```

**输出:**

```
2019-04-28T19:58:13.775Z[Etc/UTC]
2015-01-31T19:58:13.775Z[Etc/UTC]

```

**节目 2** :举例说明异常。下面的程序抛出一个异常，因为 2 月是 28 天，而不是 31 天。

```
// Program to illustrate the adjustInto() method
// Exception Program

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        try {
            ZonedDateTime date
                = ZonedDateTime.now();

            // prints the date
            System.out.println(date);

            // Parses the date
            ChronoLocalDate date1
                = LocalDate.parse("2015-02-31");

            // Uses the function to adjust the date
            date = (ZonedDateTime)date1.adjustInto(date);

            // Prints the adjusted date
            System.out.println(date);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
2019-04-28T19:58:17.219Z[Etc/UTC]
java.time.format.DateTimeParseException: Text '2015-02-31' could not be parsed: Invalid date 'FEBRUARY 31'

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldata . html # adjustInto-Java . time . temporal-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#adjustInto-java.time.temporal.Temporal-)