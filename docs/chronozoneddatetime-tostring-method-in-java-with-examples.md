# Java 中的 ChronoZonedDateTime toString()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-tostring-method-in-java-with-examples/)

**时区数据时间**接口的 **toString()** 方法用于将该时区数据时间转换为字符串表示。

**语法:**

```
String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**此方法返回 **[字符串](https://www.geeksforgeeks.org/string-class-in-java/)** ，这是此时区的字符串表示。

下面的程序说明了 toString()方法:

**程序 1:**

```
// Java program to demonstrate
// ChronoZonedDateTime.toString() method

import java.time.*;
import java.time.chrono.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime object
        ChronoZonedDateTime time
            = ZonedDateTime
                  .parse(
                      "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime: "
                           + time);

        // print result
        System.out.println("String: "
                           + time.toString());
    }
}
```

**输出:**

```
ChronoZonedDateTime: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]
String: 2018-12-06T19:21:12.123+05:30[Asia/Calcutta]

```

**程序二:**

```
// Java program to demonstrate
// ChronoZonedDateTime.toString() method

import java.time.*;
import java.time.chrono.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create ChronoZonedDateTime object
        ChronoZonedDateTime time
            = ZonedDateTime.parse(
                "1918-10-25T23:12:38.543+02:00[Europe/Paris]");

        // print ChronoZonedDateTime
        System.out.println("ChronoZonedDateTime: "
                           + time);

        // print result
        System.out.println("String: "
                           + time.toString());
    }
}
```

**输出:**

```
ChronoZonedDateTime: 1918-10-25T23:12:38.543Z[Europe/Paris]
String: 1918-10-25T23:12:38.543Z[Europe/Paris]

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitoredatetime . html # tostring】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#toString--)