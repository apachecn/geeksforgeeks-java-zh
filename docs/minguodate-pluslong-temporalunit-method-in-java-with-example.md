# Java 中的 minuodate plus(long，TemporalUnit)方法，示例

> 原文:[https://www . geeksforgeeks . org/minuodate-plus long-tempalalunit-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-pluslong-temporalunit-method-in-java-with-example/)

**Java . time . chrono . mingodate**类的 **plus()** 方法，用于在当前的 mingodate 上加上一定数量的时态取值单位后得到 mingodate。

**语法:**

```
public MinguoDate plus(long amount,
                       TemporalUnit unit)

```

**参数**:该方法以以下参数为参数:

*   **金额:**为时间单位的**金额，与当前民国日期相加。**
*   **单位:**是时间单位或时辰单位的**对象。**

**返回值:**该方法将当前的民国日期加上一定量的时态取值单位后，返回**民国日期**。

下面举例说明**加()**的方法:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// plus() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.of(1345, 06, 23);

            // display the result
            System.out.println("old Minguo date : "
                               + hidate);

            // adding some amount in Minguo date
            // by using minus() method
            MinguoDate newdate
                = hidate.plus(
                    22,
                    ChronoUnit.DAYS);

            // display the result
            System.out.println("new Minguo date : "
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
old Minguo date : Minguo ROC 1345-06-23
new Minguo date : Minguo ROC 1345-07-15

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// plus() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate
                = MinguoDate.of(1345, 06, 23);

            // display the result
            System.out.println("old Minguo date : "
                               + hidate);

            // adding some amount in Minguo date
            // by using minus() method
            MinguoDate newdate
                = hidate.plus(
                    4,
                    ChronoUnit.DECADES);

            // display the result
            System.out.println("new Minguo date : "
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
old Minguo date : Minguo ROC 1345-06-23
new Minguo date : Minguo ROC 1385-06-23

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # plus-long-Java . time . temporalunit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#plus-long-java.time.temporal.TemporalUnit-)