# Java 中的 LocalDate minusMonths()方法，示例

> 原文:[https://www . geesforgeks . org/local date-MINUS months-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-minusmonths-method-in-java-with-examples/)

Java 中 **LocalDate** 类的 **minusMonths()** 方法用于从这个 LocalDate 中减去指定的月数，并返回 LocalDate 的副本。
此方法在以下步骤中减去月份字段:

*   从年月字段中减去月份。
*   检查减去月份后的日期是否有效。
*   如果日期无效，则方法将月日调整为最后一个有效日期。

例如，2018-07-31 减去一个月给出了日期 2018-06-31，但这是无效的结果，因此返回该月的最后一个有效日期 2018-06-30。此实例是不可变的，不受此方法调用的影响。

**语法:**

```
public LocalDate minusMonths(long monthsToSubtract)

```

**参数:**该方法接受单个参数 **monthsToSubtract** ，代表要减去的月份，可以是负数。

**返回值:**该方法返回一个基于该日期减去月份的**本地日期**，不为空。

**异常:**如果结果超出支持的日期范围，该方法抛出**日期时间异常**。

以下程序说明了最小月()方法:
**程序 1:**

```
// Java program to demonstrate
// LocalDate.minusMonths() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-11-13");

        // print instance
        System.out.println("LocalDate before"
                           + " subtracting months: " + date);

        // subtract 15 months
        LocalDate returnvalue
            = date.minusMonths(15);

        // print result
        System.out.println("LocalDate after "
                           + " subtracting months: " + returnvalue);
    }
}
```

**Output:**

```
LocalDate before subtracting months: 2018-11-13
LocalDate after  subtracting months: 2017-08-13

```

**程序 2:**

```
// Java program to demonstrate
// LocalDate.minusMonths() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate date
            = LocalDate.parse("2018-12-31");

        // print instance
        System.out.println("LocalDate before"
                           + " subtracting months: " + date);

        // subtract 3 months
        LocalDate returnvalue
            = date.minusMonths(3);

        // print result
        System.out.println("LocalDate after "
                           + " subtracting months: " + returnvalue);
    }
}
```

**Output:**

```
LocalDate before subtracting months: 2018-12-31
LocalDate after  subtracting months: 2018-09-30

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # minustomorks(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#minusMonths(long))