# Java 中的 minuodate now(ZoneId)方法，示例

> 原文:[https://www . geeksforgeeks . org/minuodate-now zoneid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/minguodate-nowzoneid-method-in-java-with-examples/)

**Java . time . chrono . mingodate**类的 **now()** 方法，用于根据指定区域的民国日历系统获取当前的民国日期。

**语法:**

```
public static MinguoDate now(ZoneId zone)

```

**参数**:该方法以**区域 id** 为对象，在此基础上形成民国日期。

**返回值:**此方法从指定时钟根据民国日历系统返回当前**民国日期**。

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

            // Creating and initializing ZoneId
            ZoneId id = ZoneId.systemDefault();

            // Creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now(id);

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

            // Creating and initializing ZoneId
            ZoneId id = ZoneId.of("Z");

            // Creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.now(id);

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

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # now-Java . time . zoneid-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#now-java.time.ZoneId-)