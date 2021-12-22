# Java 中的 Duration getSeconds()方法，示例

> 原文:[https://www . geesforgeks . org/duration-getseconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-getseconds-method-in-java-with-examples/)

**java.time 包**中**时长类**的 **getSeconds()** 方法用于获取该时长的第二个值。

**语法:**

```java
public long getSeconds()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个**长值**这个持续时间的秒数。

以下示例说明了 Duration.getSeconds()方法:

**例 1:**

```java
// Java code to illustrate getSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P2DT3H4M";

        // Duration using parse() method
        Duration duration = Duration.parse(time);

        // Get the duration in seconds
        // using getSeconds() method
        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```java
183840

```

**例 2:**

```java
// Java code to illustrate getSeconds() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofHours() method
        Duration duration = Duration.ofHours(5);

        // Get the duration in seconds
        // using getSeconds() method
        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```java
18000

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#getSeconds--)