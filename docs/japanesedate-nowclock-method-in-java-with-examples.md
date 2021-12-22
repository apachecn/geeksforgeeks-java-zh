# Java 中的日本现在日期(时钟)方法，示例

> 原文:[https://www . geesforgeks . org/japanesedate-now clock-in-Java-method-with-examples/](https://www.geeksforgeeks.org/japanesedate-nowclock-method-in-java-with-examples/)

**Java . time . chrono . japanesedate**类的 **now()** 方法用于从指定的时钟获取根据日本日历系统的当前日本日期。

**语法:**

```
public static JapaneseDate now(Clock clock)

```

**参数**:该方法以**时钟**为对象，在此基础上形成日本日期。

**返回值:**此方法从指定的时钟根据日本日历系统返回当前的**日本日期**。

以下是举例说明**现在()**方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate now() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing clock
            Clock clock = Clock.systemUTC();

            // Creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now(clock);

            // Display the result
            System.out.println("JapaneseDate: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:**

```
JapaneseDate: Japanese Heisei 32-03-23

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate now() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing clock
            Clock clock = Clock.systemDefaultZone();

            // Creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now(clock);

            // Display the result
            System.out.println("JapaneseDate: "
                               + hidate);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:**

```
JapaneseDate: Japanese Heisei 32-03-23

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # now-Java . time . clock-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#now-java.time.Clock-)