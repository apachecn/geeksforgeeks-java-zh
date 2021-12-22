# Java 中的 Date compareTo()方法，带示例

> 原文:[https://www . geesforgeks . org/date-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/date-compareto-method-in-java-with-examples/)

**Java Date 类**的 **compareTo()** 方法比较两个日期并排序。

**语法:**

```
public int compareTo(Date anotherDate)

```

**参数:**该函数接受单个参数**另一个日期**，该参数指定要比较的日期。

**返回值:**该函数给出以下指定的三个返回值:

*   如果参数“日期”等于该日期，则返回值 0。
*   如果此日期在日期参数之前，则返回小于 0 的值。
*   如果此日期在日期参数之后，它将返回一个大于 0 的值。

**异常:**如果**另一个日期**为空，函数抛出一个异常，即**空指针异常**。

下面的程序演示了上述功能:

```
// Java code to demonstrate
// compareTo() function of Date class

import java.util.Date;
import java.util.Calendar;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a Calendar object
        Calendar c = Calendar.getInstance();

        // set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c.set(Calendar.MONTH, 11);

        // set Date
        c.set(Calendar.DATE, 05);

        // set Year
        c.set(Calendar.YEAR, 1996);

        // creating a date object with specified time.
        Date dateOne = c.getTime();

        System.out.println("Date 1: "
                           + dateOne);

        // creating a date of object
        // storing the current date
        Date currentDate = new Date();

        System.out.println("Date 2: "
                           + currentDate);

        // compares
        System.out.println("On Comparison: "
                           + currentDate
                                 .compareTo(dateOne));
    }
}
```

**Output:**

```
Date 1: Thu Dec 05 08:17:55 UTC 1996
Date 2: Wed Jan 02 08:17:55 UTC 2019
On Comparison: 1

```

```
// Java code to demonstrate
// compareTo() function of Date class

import java.util.Date;

public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a date of object
        // stospecified datent date
        Date currentDate = new Date();

        System.out.println("Date 1: " + currentDate);

        // specifiedDate is assigned to null.
        Date specifiedDate = null;

        System.out.println("Date 2: " + specifiedDate);

        System.out.println("Passing null as parameter: ");
        try {
            // throws NullPointerException
            System.out.println(currentDate
                                   .compareTo(specifiedDate));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Date 1: Wed Jan 02 08:18:02 UTC 2019
Date 2: null
Passing null as parameter: 
Exception: java.lang.NullPointerException

```