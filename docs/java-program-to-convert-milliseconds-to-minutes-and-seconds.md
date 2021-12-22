# 将毫秒转换为分和秒的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到转换-毫秒到分和秒/](https://www.geeksforgeeks.org/java-program-to-convert-milliseconds-to-minutes-and-seconds/)

在 java 中，使用类似 [toMinutes()](https://www.geeksforgeeks.org/timeunit-tominutes-method-in-java-with-examples/) 和 [toSeconds()](https://www.geeksforgeeks.org/timeunit-toseconds-method-in-java-with-examples/) 的方法将毫秒转换为分钟和秒，时间单位在[并发包](https://www.geeksforgeeks.org/java-util-concurrent-package/)中。

**毫秒:**

```
1 millisecond = 0.001 second or (1/1000) seconds
```

**秒:**

```
1 second = 1000 millisecond
1 second = (1/60) minutes
```

**分钟:**

```
1 minute = 60000 milliseconds
1 minute = 60 seconds
1 minute = (1/60)hour
```

**例:**

```
Input : Milliseconds = 400000
Output: 6 minutes and 40 seconds

Input : Milliseconds = 5400000
Output: 90 minutes and 0 seconds
```

**算法** :

1.  Enter in milliseconds.
2.  Use the formula to convert milliseconds to minutes: minutes = (milliseconds /1000)/60).
3.  Use the formula to convert milliseconds to seconds: seconds = (milliseconds /1000)%60).
4.  Print from milliseconds to minutes.

**求解方法:** Java 程序将毫秒转换为分和秒。

1.  Use basic input and output in simple Java.
2.  Use the methods in Java.

**1。将毫秒转换为分钟和秒的程序**

## Java

```
// Java Program to Convert Milliseconds
// to Minutes and Seconds

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Take Input in Long otherwise
        // overflow occur for some inputs.
        long milliseconds = 3500000;

        // formula for conversion for
        // milliseconds to minutes.
        long minutes = (milliseconds / 1000) / 60;

        // formula for conversion for
        // milliseconds to seconds
        long seconds = (milliseconds / 1000) % 60;

        // Print the output
        System.out.println(milliseconds + " Milliseconds = "
                           + minutes + " minutes and "
                           + seconds + " seconds.");
    }
}
```

**输出**

```
3500000 Milliseconds = 58 minutes and 20 seconds.
```

**2。使用方法将毫秒转换为分钟** **和秒的程序。**

## Java

```
// Java Program to Convert Milliseconds
// to Minutes and Seconds

import java.io.*;
import java.util.concurrent.TimeUnit;

class GFG {
    public static void main(String[] args)
    {
        long milliseconds = 3500000;

        // This method uses this formula :minutes =
        // (milliseconds / 1000) / 60;
        long minutes
            = TimeUnit.MILLISECONDS.toMinutes(milliseconds);

        // This method uses this formula seconds =
        // (milliseconds / 1000);
        long seconds
            = (TimeUnit.MILLISECONDS.toSeconds(milliseconds)
               % 60);

        // Print the answer
        System.out.format(milliseconds + " Milliseconds = "
                          + minutes + " minutes and "
                          + seconds + " seconds");
    }
}
```

**输出**

```
3500000 Milliseconds = 58 minutes and 20 seconds
```