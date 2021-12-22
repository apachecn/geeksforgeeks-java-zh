# Java 中的 MinguoDate 减(long，TemporalUnit)方法，示例

> 原文:[https://www . geesforgeks . org/Minguo date-mins long-tempalalunit-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-minuslong-temporalunit-method-in-java-with-example/)

**Java . time . chrono . mingodate**类的**减()**方法用于从当前的 mingodate 中减去一定数量的时态访问器单位后得到 mingodate。

**语法:**

```
public MinguoDate minus(long amountToAdd,
                        TemporalUnit unit)
```

**参数**:该方法以以下参数为参数:

*   **amountToSubtract:** 是要从当前民国日期中减去的时间单位值。
*   **单位:**是时间单位或时辰单位的对象。

**返回值**:该方法从当前民国日期中减去一个时间存取器单位后返回民国日期。

以下是举例说明**减去()**方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate minus() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // Display the result
            System.out.println("old Minguo date: "
                               + hidate);

            // Subtracting Minguo date
            // by using minus() method
            MinguoDate newdate
                = hidate.minus(
                    22, ChronoUnit.DAYS);

            // Display the result
            System.out.println("new Minguo date: "
                               + newdate);
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
old Minguo date: Minguo ROC 109-04-24
new Minguo date: Minguo ROC 109-04-02
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate minus() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // Display the result
            System.out.println("old Minguo date: "
                               + hidate);

            // Subtracting Minguo date
            // by using minus() method
            MinguoDate newdate
                = hidate.minus(
                    4, ChronoUnit.DECADES);

            // Display the result
            System.out.println("new Minguo date: "
                               + newdate);
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
old Minguo date: Minguo ROC 109-04-24
new Minguo date: Minguo ROC 69-04-24
```

**参考:**