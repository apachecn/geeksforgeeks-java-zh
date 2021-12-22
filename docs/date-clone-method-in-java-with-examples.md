# Java 中的日期克隆()方法，示例

> 原文:[https://www . geesforgeks . org/date-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/date-clone-method-in-java-with-examples/)

Java 中 Date 类的 clone()方法返回传递的 Date 对象的副本。这个副本只是给定日期对象的一个浅层副本。
**语法:**

```java
public Object clone()

```

**参数:**该方法不接受任何参数。
**返回值:**该方法返回对象的克隆。
以下程序说明了克隆()方法的使用:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate
// clone() method of Date class

import java.util.Date;
import java.util.Calendar;

public class GfG {
    public static void main(String args[])
    {

        // Creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // Set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c1.set(Calendar.MONTH, 11);

        // Set Date
        c1.set(Calendar.DATE, 05);

        // Set Year
        c1.set(Calendar.YEAR, 1996);

        // Creating a date object
        // with specified time.
        Date dateOne = c1.getTime();

        Object dateTwo = dateOne.clone();

        System.out.println("Original Date: "
                           + dateOne.toString());
        System.out.println("Cloned Date: "
                           + dateTwo.toString());
    }
}
```

**Output:** 

```java
Original Date: Thu Dec 05 05:39:04 UTC 1996
Cloned Date: Thu Dec 05 05:39:04 UTC 1996

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate
// clone() method of Date class

import java.util.Date;
import java.util.Calendar;

public class GfG {
    public static void main(String args[])
    {

        // Creating a Calendar object
        Calendar c1 = Calendar.getInstance();

        // Set Month
        // MONTH starts with 0 i.e. ( 0 - Jan)
        c1.set(Calendar.MONTH, 00);

        // Set Date
        c1.set(Calendar.DATE, 30);

        // Set Year
        c1.set(Calendar.YEAR, 2019);

        // Creating a date object
        // with specified time.
        Date dateOne = c1.getTime();

        Object dateTwo = dateOne.clone();

        System.out.println("Original Date: "
                           + dateOne.toString());
        System.out.println("Cloned Date: "
                           + dateTwo.toString());
    }
}
```

**Output:** 

```java
Original Date: Wed Jan 30 05:39:10 UTC 2019
Cloned Date: Wed Jan 30 05:39:10 UTC 2019

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/date . html # clone–](https://docs.oracle.com/javase/8/docs/api/java/util/Date.html#clone--)