# Java 中的日期哈希码()方法，示例

> 原文:[https://www . geesforgeks . org/date-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/date-hashcode-method-in-java-with-examples/)

**Java 日期类**的 **hashCode()** 方法返回一个值，该值是该对象的哈希代码。

**语法:**

```
public int hashCode()

```

**参数:**函数不接受任何参数。

**返回值:**返回该对象的哈希值。

**异常:**函数不抛出任何异常。

下面的程序演示了上述功能:

```
// Java code to demonstrate
// hashCode() function of Date class

import java.util.Date;
import java.util.Calendar;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c1.set(Calendar.MONTH, 11);

        // set Date
        c1.set(Calendar.DATE, 05);

        // set Year
        c1.set(Calendar.YEAR, 1996);

        // creating a date object with specified time.
        Date dateOne = c1.getTime();

        System.out.println("Date: " + dateOne);

        // Prints hash Code
        System.out.println("HashCode: "
                           + dateOne.hashCode());
    }
}
```

**Output:**

```
Date: Thu Dec 05 08:22:04 UTC 1996
HashCode: -629399711

```

```
// Java code to demonstrate
// hashCode() function of Date class

import java.util.Date;
import java.util.Calendar;
public class GfG {
    // main method
    public static void main(String[] args)
    {

        // creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c1.set(Calendar.MONTH, 11);

        // set Date
        c1.set(Calendar.DATE, 21);

        // set Year
        c1.set(Calendar.YEAR, 1999);

        // creating a date object with specified time.
        Date dateOne = c1.getTime();

        System.out.println("Date: " + dateOne);

        // Prints hash Code
        System.out.println("HashCode: "
                           + dateOne.hashCode());
    }
}
```

**Output:**

```
Date: Tue Dec 21 08:22:09 UTC 1999
HashCode: 871724355

```