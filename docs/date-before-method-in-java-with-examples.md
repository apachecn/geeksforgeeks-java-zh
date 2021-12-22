# Java 中的 Date before()方法，示例

> 原文:[https://www . geeksforgeeks . org/date-before-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/date-before-method-in-java-with-examples/)

**Java Date 类**的 **before()** 方法测试日期是否在指定日期之前。

**语法:**

```
public boolean before(Date when)

```

**参数:**当指定需要检查的日期时，该功能接受单个参数**。**

**返回值:**返回布尔值。如果该日期在指定日期之前，它将返回 true，否则返回 false。

**异常:**当为空时，如果**为空，函数抛出一个异常，即**空指针异常**。**

下面的程序演示了上述功能:

```
// Java code to demonstrate
// before() function of Date class

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

        System.out.println("Date 1: " + dateOne);

        // creating a date of object
        // storing the current date
        Date currentDate = new Date();

        System.out.println("Date 2: " + currentDate);

        System.out.println("Is Date 2 before Date 1: "
                         + currentDate.before(dateOne));
    }
}
```

**Output:**

```
Date 1: Thu Dec 05 08:15:01 UTC 1996
Date 2: Wed Jan 02 08:15:01 UTC 2019
Is Date 2 before Date 1: false

```

```
// Java code to demonstrate
// before() function of Date class

import java.util.Date;

public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a date of object
        // storing the current date
        Date currentDate = new Date();

        System.out.println("Date 1: " + currentDate);

        // specifiedDate is assigned to null.
        Date specifiedDate = null;

        System.out.println("Date 1: " + specifiedDate);

        System.out.println("On checking these 2 dates: ");

        try {
            // throws NullPointerException
            System.out.println(currentDate
                                   .before(specifiedDate));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```
Date 1: Wed Jan 02 08:15:06 UTC 2019
Date 1: null
On checking these 2 dates: 
Exception: java.lang.NullPointerException

```