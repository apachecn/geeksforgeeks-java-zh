# Java 中的 HijrahDate now(时钟)方法，示例

> 原文:[https://www . geesforgeks . org/hijrahdate-now clock-in-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahdate-nowclock-method-in-java-with-example/)

**Java . time . chrono . hijrahdate**类的 **now()** 方法用于从指定的时钟中根据 hijrah 日历系统获取当前的 hijrah 日期。

**语法:**

```
public static HijrahDate now(Clock clock)

```

**参数**:该方法以**时钟**为对象，在此基础上形成回历日期。

**返回值:**该方法根据回历系统从指定的时钟返回当前**回历日期**。

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
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now(clock);

            // Display the result
            System.out.println("HijrahDate: "
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
HijrahDate: Hijrah-umalqura AH 1441-06-25

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// now() method

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
            Clock clock
                = Clock.systemDefaultZone();

            // Creating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now(clock);

            // Display the result
            System.out.println("HijrahDate: "
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
HijrahDate: Hijrah-umalqura AH 1441-06-25

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrahdate . html # now-Java . time . clock-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#now-java.time.Clock-)