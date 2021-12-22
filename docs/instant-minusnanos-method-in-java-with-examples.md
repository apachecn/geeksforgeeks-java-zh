# Java 中的瞬间微纳()方法，示例

> 原文:[https://www . geeksforgeeks . org/instant-mins nano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-minusnanos-method-in-java-with-examples/)

**瞬间类**的亚纳秒()方法从这个瞬间减去作为参数传递的纳秒值，并将结果作为瞬间对象返回。这个返回的即时消息是不可变的。
**语法:**

```java
public Instant minusNanos(long nanosToSubtract)
```

**参数:**该方法接受一个参数**nanotosubtract**，需要减去纳秒。
**返回:**此方法在减去纳秒后返回**瞬间**。
**异常:**此方法抛出以下异常:

*   **DateTimeException** :如果结果超过最大或最小瞬间。
*   **算术异常**:如果出现数值溢出。

下面的程序说明了亚纳米()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Instant.minusNanos() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // current Instant
        System.out.println("Initialize instant: "
                           + instant);

        // subtract 430000000 nanoseconds
        // means .43 seconds from this instant
        Instant returnedValue
            = instant.minusNanos(430000000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

**Output**

```java
Initialize instant: 2018-12-30T19:34:50.630Z
Returned Instant: 2018-12-30T19:34:50.200Z

```