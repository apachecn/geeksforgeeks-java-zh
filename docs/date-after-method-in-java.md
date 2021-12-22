# Java 中的 Date after()方法

> 原文:[https://www.geeksforgeeks.org/date-after-method-in-java/](https://www.geeksforgeeks.org/date-after-method-in-java/)

**java.util.Date.after()** 方法用于检查日期的当前实例是否在指定日期之后。

**语法:**

```java
dateObject.after(Date specifiedDate)

```

**参数:**只取一个参数**指定数据类型日期的**。这是要与调用函数的日期实例进行比较的日期。

**返回值:**该函数的返回类型为**布尔型**。如果日期的当前实例严格大于指定日期，则返回 *true* 。否则返回*假*。

**异常:**如果指定的数据为空，这个方法将在调用时抛出**空指针异常**。

下面的程序说明了 Date 类中的 after()方法:

**程序 1:**

```java
// Java code to demonstrate
// after() function of Date class

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

        // creating a date of object
        // storing the current date
        Date currentDate = new Date();

        System.out.print("Is currentDate after date one : ");

        // if currentDate is after dateOne
        System.out.println(currentDate.after(dateOne));
    }
}
```

**Output:**

```java
Is currentDate after date one : true

```

**程序 2:** 演示 java.lang.NullPointerException

```java
// Java code to demonstrate
// after() function of Date class

import java.util.Date;

public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a date of object
        // storing the current date
        Date currentDate = new Date();

        // specifiedDate is assigned to null.
        Date specifiedDate = null;

        System.out.println("Passing null as parameter : ");
        try {
            // throws NullPointerException
            System.out.println(currentDate.after(specifiedDate));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Passing null as parameter : 
Exception: java.lang.NullPointerException

```