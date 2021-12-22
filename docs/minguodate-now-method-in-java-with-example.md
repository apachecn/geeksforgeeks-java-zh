# Java 中的 MinguoDate now()方法，示例

> 原文:[https://www . geesforgeks . org/minuodate-now-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-now-method-in-java-with-example/)

**Java . time . chrono . mingodate**类的 **now()** 方法，用于从指定的时钟获取根据民国日历系统的当前民国日期。

**语法:**

```
public static MinguoDate now(Clock clock)

```

**参数**:该方法取时钟的对象，在此基础上将形成民国日期。

**返回值**:该方法从指定的时钟根据民国日历系统返回当前的民国日期。

以下是举例说明**现在()**方法:

T4】例 1:

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
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now(clock);

            // Display the result
            System.out.println("MinguoDate: "
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
MinguoDate: Minguo ROC 109-04-24

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
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now(clock);

            // Display the result
            System.out.println("MinguoDate: "
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
MinguoDate: Minguo ROC 109-04-24

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # now-Java . time . clock-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#now-java.time.Clock-)