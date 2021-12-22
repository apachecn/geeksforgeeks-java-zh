# Java 中的 HijrahDate 减(长，临时)方法，示例

> 原文:[https://www . geesforgeks . org/hijrahdate-mins long-tempalalunit-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahdate-minuslong-temporalunit-method-in-java-with-example/)

**Java . time . chrono . HijrahDate**类的**减()**方法用于在从当前 hijrah date 中减去一定数量的时态访问器单位后获取 hijrah date。

**语法:**

```java
public HijrahDate minus(long amountToSubtract,
                        TemporalUnit unit)
```

**参数**:该方法以下列参数为参数:

*   **Amount to Subtract:** is the time unit value to be subtracted from the current Hijra date.
*   **Unit:** is an object of time unit or hour unit.

**返回值:**此方法在当前回历日期减去一个时间存取器单位后，返回**回历日期**。

以下是举例说明**减去()**方法的例子:

**例 1:**

## 爪哇

```java
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
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // Display the result
            System.out.println("old hijrah date: "
                               + hidate);

            // Subtracting hijrah date
            // by using minus() method
            HijrahDate newdate
                = hidate.minus(
                    22, ChronoUnit.DAYS);

            // Display the result
            System.out.println("new hijrah date: "
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

**输出:**

```java
old hijrah date: Hijrah-umalqura AH 1441-06-25
new hijrah date: Hijrah-umalqura AH 1441-06-03
```

**例二:**

## 爪哇

```java
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
            // Dreating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.now();

            // Display the result
            System.out.println("old hijrah date: "
                               + hidate);

            // Subtracting hijrah date
            // by using minus() method
            HijrahDate newdate
                = hidate.minus(
                    4, ChronoUnit.DECADES);

            // Display the result
            System.out.println("new hijrah date: "
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

**输出:**

```java
old hijrah date: Hijrah-umalqura AH 1441-06-25
new hijrah date: Hijrah-umalqura AH 1401-06-25
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrahdate . html #减-long-Java . time . temporalunit-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#minus-long-java.time.temporal.TemporalUnit-)