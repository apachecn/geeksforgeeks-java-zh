# Java 中的持续时间至秒()方法，示例

> 原文:[https://www . geesforgeks . org/duration-to seconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-toseconds-method-in-java-with-examples/)

使用 **java.time 包**中**持续时间类**的**至**方法，以秒为单位获取该持续时间的值。

**语法:**

```java
public long toSeconds()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个**长值**，即该时长内的秒数。

以下示例说明了 Duration.toSeconds()方法:

**例 1:**

```java
// Java code to illustrate toSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        System.out.println("Duration: "
                           + duration);

        // Get the number of seconds
        // using toSeconds() method
        System.out.println(duration.toSeconds());
    }
}
```

**输出:**

```java
Duration: PT51H4M
183840

```

**例 2:**

```java
// Java code to illustrate toSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofSeconds() method
        Duration duration
            = Duration.ofSeconds(10);

        System.out.println("Duration: "
                           + duration);

        // Get the number of seconds
        // using toSeconds() method
        System.out.println(duration.toSeconds());
    }
}
```

**输出:**

```java
Duration: PT10S
10

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # to seconds–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toSeconds--)