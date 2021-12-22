# Java 中的 Instant ofEpochSecond()方法，带示例

> 原文:[https://www . geeksforgeeks . org/instant-ofepochssecond-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-ofepochsecond-method-in-java-with-examples/)

在 Instant 类中，根据传递给它的参数，有两种类型的 ofEpochSecond()方法。

### 每秒钟(长时间)

**一个 **Instant** 类的方法，用于返回 Instant 的一个实例，该实例将秒作为参数传递给从 1970-01-01T00:00:00Z 的纪元开始计算的方法。纳秒字段设置为零。**

**语法:**

```
public static Instant ofEpochSecond(long epochSecond)

```

**参数:**该方法只接受一个参数 **epochSecond** ，即 1970-01-01T00:00:00Z 的秒数。

**返回值:**该方法以秒为参数返回**瞬间**。

**异常:**如果瞬间超过最大或最小瞬间，该方法抛出以下异常**日期时间异常**。

以下程序说明了 ofEpochSecond()方法:
**程序 1:**

```
// Java program to demonstrate
// Instant.ofEpochSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // long epochsecond value
        long epochSecond = 1200000l;

        // apply ofEpochSecond method of Instant class
        Instant result
            = Instant.ofEpochSecond(epochSecond);

        // print results
        System.out.println("Instant: "
                           + result);
    }
}
```

**Output:**

```
Instant: 1970-01-14T21:20:00Z

```

### 十亿秒(长时间的十亿秒，长时间的纳米调整)

**of Pocchssecond()**一个 **Instant** 类的方法，用于返回 Instant 的一个实例，使用秒作为参数传递给从 1970-01-01T00:00:00Z 的纪元开始计算的方法，纳秒的分数秒也作为参数传递，这将改变秒和纳秒的值，以确保存储的纳秒在 0 到 999，999，999 的范围内。

**语法:**

```
public static Instant ofEpochSecond(long epochSecond,
                                    long nanoAdjustment)

```

**参数:**该方法接受两个参数 **epochSecond** 和 **nanoAdjustment** ，前者是从 1970-01-01T00:00:00Z 开始的秒数，后者是对秒数的纳秒级调整，正或负。

**返回值:**该方法以秒为参数返回**瞬间**。

**异常:**该方法抛出以下异常:

*   **日期时间异常**–如果瞬间超过最大或最小瞬间。
*   **算术异常**–如果出现数值溢出。

以下程序说明了 ofEpochSecond()方法:
**程序 1:**

```
// Java program to demonstrate
// Instant.ofEpochSecond() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // long epochsecond value and nanoadjustment value
        long epochSecond = 1200000000l;
        long nanoadjustment = 999999l;

        // apply ofEpochSecond method of Instant class
        Instant result
            = Instant.ofEpochSecond(epochSecond,
                                    nanoadjustment);

        // print results
        System.out.println("Instant: "
                           + result);
    }
}
```

**Output:**

```
Instant: 2008-01-10T21:20:00.000999999Z

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # ofEpochSecond(长，长)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#ofEpochSecond(long, long))
[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # ofEpochSecond(长)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#ofEpochSecond(long))