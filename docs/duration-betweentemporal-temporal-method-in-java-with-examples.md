# Java 中(时态、时态)方法之间的持续时间，示例

> 原文:[https://www . geeksforgeeks . org/duration-temporal-temporal-in-Java-method-with-examples/](https://www.geeksforgeeks.org/duration-betweentemporal-temporal-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**(时态)**方法用于获取作为参数传递的两个时态对象之间的持续时间。第一个参数包含在内，而第二个参数不包含在计算中。如果对象的类型不同，则持续时间将根据第一个对象的类型计算。

**语法:**

```
public static Duration between(Temporal startDuration, Temporal endDuration)

```

**参数:**该方法接受两个参数:

*   **Start duration** : that is, the start moment to be calculated. It is included in the calculation. It should not be empty.
*   **End duration** : that is, the end moment to be calculated. It is unique in the calculation. It should not be empty.

**返回值:**该方法返回一个**持续时间**，代表作为参数传递的时刻之间经过的时间。

**异常:**此方法抛出:

*   **Abnormal date and time** : If the number of seconds in the time interval cannot be obtained.
*   **Arithmetic exception** : If the calculation exceeds the capacity of the duration.

以下示例说明了 Duration.between()方法:

**例 1:**

```
// Java code to illustrate between() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using between() method
        Duration duration
            = Duration.between(LocalTime.MIDNIGHT,
                               LocalTime.NOON);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```
43200

```

**例 2:**

```
// Java code to illustrate between() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using between() method
        Duration duration
            = Duration.between(LocalTime.NOON,
                               LocalTime.MAX);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```
43199

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#between-java.time.temporal.Temporal-java.time.temporal.Temporal-)