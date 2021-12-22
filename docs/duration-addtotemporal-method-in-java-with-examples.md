# Java 中的 Duration addTo(时态)方法，示例

> 原文:[https://www . geesforgeks . org/duration-addtotemporal-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-addtotemporal-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **addTo(时态)**方法用于将该持续时间添加到指定的时态对象中，作为参数传递。

**语法:**

```
public Temporal addTo?(Temporal temporalObject)

```

**参数:**此方法接受一个参数**时间对象**，即在此持续时间内需要调整的量。它不应为空。

**返回值:**该方法返回一个相同类型的**对象**，并对其进行时间对象调整。

**异常:**此方法抛出:

*   日期时间异常:唉呀呀呀呀呀呀呀呀呀呀。
*   **Arithmetic exception** : If there is a numerical overflow.

以下示例说明了 Duration.addTo()方法:

**例 1:**

```
// Java code to illustrate addTo() method

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
        // using addTo() method
        System.out.println(
            duration1
                .addTo(currentTime));
    }
}
```

**输出:**

```
Original time: 2018-11-26T07:01:13.535
2018-11-28T10:05:13.535

```

**例 2:**

```
// Java code to illustrate addTo() method

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
        // using addTo() method
        System.out.println(
            duration2
                .addTo(currentTime));
    }
}
```

**输出:**

```
Original time: 2018-11-26T07:01:16.615
2018-11-21T07:01:16.615

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#addTo-java.time.temporal.Temporal-)