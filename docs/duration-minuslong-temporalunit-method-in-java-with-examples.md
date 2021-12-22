# Java 中的持续时间减(长，时间单位)方法，示例

> 原文:[https://www . geesforgeks . org/duration-mins long-tempalalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-minuslong-temporalunit-method-in-java-with-examples/)

**java.time 包**中 **Duration 类**的**减(long，TemporalUnit)** 方法用于获取该持续时间的不可变副本，减去指定的持续时间，作为参数传递。要减去的持续时间是通过将作为参数传递的单位中的数量转换为数量来决定的。

**语法:**

```
public Duration minus(long amountToAdd, TemporalUnit unit)
```

**参数:**该方法接受两个参数:

*   **金额增加**是要减去的金额。它可以是正数或负数，但不能为空。
*   **单位**，是要减去的金额的时间单位。它不能为空。

**返回值:**该方法返回一个**持续时间**，它是一个现有持续时间的不可变副本，并减去持续时间的参数量。

**异常:**此方法抛出:

*   **算术异常**:如果出现数值溢出。
*   **如果不支持该单元，则不支持该单元。**

以下示例说明了 Duration .减()方法:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate minus() method

import java.time.Duration;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration subtracted
        // using minus() method
        System.out.println(duration1
                               .minus(5,
                                      ChronoUnit.HOURS));
    }
}
```

**Output:** 

```
PT46H4M
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate minus() method

import java.time.Duration;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration subtracted
        // using minus() method
        System.out.println(duration1
                               .minus(2,
                                      ChronoUnit.DAYS));
    }
}
```

**Output:** 

```
PT-47H-56M
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html #减-long-Java . time . temporal unit-T4】