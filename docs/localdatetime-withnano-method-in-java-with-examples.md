# Java 中带有 Nano()方法的 LocalDateTime，示例

> 原文:[https://www . geesforgeks . org/local datetime-with nano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-withnano-method-in-java-with-examples/)

Java 中 [LocalDateTime 类](https://www.geeksforgeeks.org/java-time-localdate-class-in-java/)的 **withNano()** 方法用来获取这个 LocalDateTime 的副本，其中 nano-seconds 改为 nano-seconds 作为参数传递给这个方法。该本地日期时间的其余值保持不变。

**语法:**

```
public LocalDateTime withNano(int nanoSeconds)
```

**参数:**单个强制参数**纳秒**，指定要在结果本地日期时间实例中设置的纳米秒。这些纳米秒的值的范围可以从 0 到 999999999。

**返回类型:**一个**本地日期时间实例**，将纳米秒更改为纳米秒作为参数传递给该方法。该本地日期时间的其余值保持不变。

**异常**:如果纳米秒值无效，该功能会抛出**日期时间异常**。

**例**T2【1:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate withNano() method of
// LocalDateTime class

// Importing required classes
import java.time.*;
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating tan instance of LocalDateTime class
        LocalDateTime dt = LocalDateTime.now();

        // Getting the String representation of this
        // LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + dt.toString());

        // Getting a new LocalDateTime with nano-seconds 0
        System.out.println("New LocalDateTime: "
                           + dt.withNano(0));
    }
}
```

**Output:** 

```
Original LocalDateTime: 2018-11-30T12:54:17.484
New LocalDateTime: 2018-11-30T12:54:17
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate withNano() method of
// LocalDateTime class

// Importing required classes
import java.time.*;
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of LocalDateTime class inside
        // main()
        LocalDateTime dt
            = LocalDateTime.parse("2015-04-06T10:15:30");

        // Getting the String representation of this
        // LocalDateTime
        System.out.println("Original LocalDateTime: "
                           + dt.toString());

        // Getting a new LocalDateTime with nano-seconds
        // 99999
        System.out.println("New LocalDateTime: "
                           + dt.withNano(99999));
    }
}
```

**Output:** 

```
Original LocalDateTime: 2015-04-06T10:15:30
New LocalDateTime: 2015-04-06T10:15:30.000099999
```

> 现在我们将小心处理 Nano(0)方法用于去除 Nano 秒并保留日期时间至秒。

**例 3:**

> **注意:特殊情况:**如果秒值为:00，那么在 toString()上做的同时会消除秒部分。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate withNano() method of
// LocalDateTime class

// Importing required classes
import java.io.*;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
        throws InterruptedException
    {

        // Creating an object of DateTimeFormatter class
        DateTimeFormatter dtf
            = DateTimeFormatter.ISO_DATE_TIME;

        // If condition holds true
        while (true) {

            // Making thread to sleep for 500 nanoseconds
            Thread.sleep(500);

            // Print and display commands
            System.out.println("Original :00 seconds --> "
                               + LocalDateTime.now());
            System.out.println(
                "Without Formatter(Observe when seconds is :00) --> "
                + LocalDateTime.now().withNano(0));
            System.out.println(
                "With Formatter -> "
                + LocalDateTime.now().withNano(0).format(
                    dtf));
        }
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-250137-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211028200053/spl_case.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211028200053/spl_case.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211028200053/spl_case.mp4)</video>