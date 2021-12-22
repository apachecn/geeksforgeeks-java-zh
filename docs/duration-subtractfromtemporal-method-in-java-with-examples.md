# Java 中的持续时间减法(时态)方法，示例

> 原文:[https://www . geesforgeks . org/duration-减法 frontimporal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-subtractfromtemporal-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**减法从(时态)**方法用于将该持续时间减去指定的时态对象，作为参数传递。

**语法:**

```java
public Temporal subtractFrom?(Temporal temporalObject)

```

**参数:**此方法接受一个参数**时间对象**，即在此持续时间内需要调整的量。它不应为空。

**返回值:**该方法返回一个相同类型的**对象**，并对其进行时间对象调整。

**异常:**此方法抛出:

*   **Abnormal date and time** : If the subtraction is not possible.
*   **Arithmetic exception** : If there is a numerical overflow.

以下示例说明了 Duration .减法 From()方法:

**例 1:**

```java
// Java code to illustrate subtractFrom() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the time to be adjusted
        LocalDateTime currentTime
            = LocalDateTime.now();

        System.out.println("Original time: "
                           + currentTime);

        // Adjust the time
        // using subtractFrom() method
        System.out.println(
            duration1
                .subtractFrom(currentTime));
    }
}
```

**输出:**

```java
Original time: 2018-11-26T06:48:30.256
2018-11-24T03:44:30.256

```

**例 2:**

```java
// Java code to illustrate subtractFrom() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration
        Duration duration2
            = Duration.ofDays(-5);

        // Get the time to be adjusted
        LocalDateTime currentTime
            = LocalDateTime.now();

        System.out.println("Original time: "
                           + currentTime);

        // Adjust the time
        // using subtractFrom() method
        System.out.println(
            duration2
                .subtractFrom(currentTime));
    }
}
```

**输出:**

```java
Original time: 2018-11-26T06:48:33.319
2018-12-01T06:48:33.319

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html #减法 from-Java . time . temporal-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#subtractFrom-java.time.temporal.Temporal-)