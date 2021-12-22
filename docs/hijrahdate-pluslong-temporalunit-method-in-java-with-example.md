# Java 中的 HijrahDate plus(long，TemporalUnit)方法，示例

> 原文:[https://www . geesforgeks . org/hijrahdate-plus long-tempalalunit-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahdate-pluslong-temporalunit-method-in-java-with-example/)

**Java . time . chrono . HijrahDate**类的 **plus()** 方法用于在当前 hijrah date 上添加一定数量的时态存取单元后获取 hijrah date。

**语法:**

```
public HijrahDate plus(long amount,
                       TemporalUnit unit)

```

**参数**:该方法以以下参数为参数:

*   **金额:**是时间单位的**金额，将与当前回历日期相加。**
*   **单位:**是时间单位或时辰单位的**对象。**

**返回值:**该方法在当前回历日期加上一定量的时间存取器单位后，返回**回历日期**。

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
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.of(1345, 06, 23);

            // display the result
            System.out.println("old hijrah date : "
                               + hidate);

            // adding some amount in hijrah date
            // by using minus() method
            HijrahDate newdate
                = hidate.plus(
                    22,
                    ChronoUnit.DAYS);

            // display the result
            System.out.println("new hijrah date : "
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
old hijrah date : Hijrah-umalqura AH 1345-06-23
new hijrah date : Hijrah-umalqura AH 1345-07-16

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
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.of(1345, 06, 23);

            // display the result
            System.out.println("old hijrah date : "
                               + hidate);

            // adding some amount in hijrah date
            // by using minus() method
            HijrahDate newdate
                = hidate.plus(
                    4,
                    ChronoUnit.DECADES);

            // display the result
            System.out.println("new hijrah date : "
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
old hijrah date : Hijrah-umalqura AH 1345-06-23
new hijrah date : Hijrah-umalqura AH 1385-06-23

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrahdate . html # plus-long-Java . time . temporalunit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#plus-long-java.time.temporal.TemporalUnit-)