# Java 中 Duration hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/duration-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-hashcode-method-in-java-with-examples/)

使用 **java.time 包**中**时长类**的 **hashCode()** 方法获取该时长的 hashCode 值。

**语法:**

```java
public int hashCode()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个**整数值**，这是这个持续时间的哈希值。

下面的例子说明了 Duration.hashCode()方法:

**例 1:**

```java
// Java code to illustrate hashCode() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration = Duration.parse("P2DT3H4M");

        // Get the hashCode value
        // using hashCode() method
        System.out.println(duration.hashCode());
    }
}
```

**输出:**

```java
183840

```

**例 2:**

```java
// Java code to illustrate hashCode() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofHours() method
        Duration duration = Duration.ofHours(5);

        // Get the hashCode value
        // using hashCode() method
        System.out.println(duration.hashCode());
    }
}
```

**输出:**

```java
18000

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#hashCode--)