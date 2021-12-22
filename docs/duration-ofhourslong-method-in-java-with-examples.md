# Java 中长时间方法的持续时间，示例

> 原文:[https://www . geesforgeks . org/duration-of hourslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-ofhourslong-method-in-java-with-examples/)

**java.time 包**中**时长类**的**hour(long)**方法用于获取 1 小时格式的时长。在这种方法中，秒以 1 小时格式的总秒计算，即每小时 3600 秒。

**语法:**

```java
public static Duration ofHours(long hours)

```

**参数:**该方法接受一个参数**小时数**，即小时数。它可以是积极的，也可以是消极的。

**返回值:**该方法返回一个**持续时间**，表示 1 小时格式的时间。

**异常:**如果输入小时数超过持续时间的容量，该方法抛出**算法异常**。

以下示例说明了 Duration.ofHours()方法:

**例 1:**

```java
// Java code to illustrate ofHours() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Hours
        long noOfHours = 5;

        // Duration using ofHours() method
        Duration duration
            = Duration.ofHours(noOfHours);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```java
18000

```

**例 2:**

```java
// Java code to illustrate ofHours() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // input number of Hours
        long noOfHours = -214545;

        // Duration using ofHours() method
        Duration duration
            = Duration.ofHours(noOfHours);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```java
-772362000

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # of hour-long-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#ofHours-long-)