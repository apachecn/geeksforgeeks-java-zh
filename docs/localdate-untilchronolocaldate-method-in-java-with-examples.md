# Java 中的 LocalDate 直到(ChronoLocalDate)方法，示例

> 原文:[https://www . geesforgeks . org/local date-untilchronolocaldate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-untilchronolocaldate-method-in-java-with-examples/)

**直到()**方法的**本地日期**类用于获取这个本地日期和作为参数传递的另一个日期之间的差异，并根据 Period 对象返回差异。此操作按年、月、日执行，并以相同方式返回答案。起点是本地日期，终点是作为参数传递的指定日期。当开始点在日期方面晚于结束点时，返回值为负。国际标准化组织日历对于这种方法非常重要，因为计算是使用国际标准化组织日历系统进行的。

**语法:**

```java
public Period until(ChronoLocalDate endDateExclusive)
```

**参数:**此方法接受一个参数 endDateExclusive，它是结束日期，Exclusive，它可以在任何年表中，它不应该为空。

**返回值:**该方法返回该日期与结束日期之间的期间。

下面的程序说明了直到()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// LocalDate.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate objects
        LocalDate l1
            = LocalDate
                  .parse("2018-12-06");

        LocalDate l2
            = LocalDate
                  .parse("2018-10-25");

        // apply until the method of LocalDate class
        Period result
            = l2.until(l1);

        // print results
        System.out.println("Result in Period: "
                           + result);
    }
}
```

**Output:** 

```java
Result in Period: P1M11D
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// LocalDate.until() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {
        // create LocalDate objects
        LocalDate l1
            = LocalDate
                  .parse("2018-12-06");

        LocalDate l2
            = LocalDate
                  .parse("2018-12-15");

        // apply until()
        Period result
            = l2.until(l1);

        // print results
        System.out.println("Result in Period: "
                           + result);
    }
}
```

**Output:** 

```java
Result in Period: P-9D
```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html #直到(Java . time . chrono . chronolocal date)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#until(java.time.chrono.ChronoLocalDate))