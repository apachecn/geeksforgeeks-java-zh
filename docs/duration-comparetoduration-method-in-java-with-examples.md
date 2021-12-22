# 持续时间比较 Java 中的(持续时间)方法示例

> 原文:[https://www . geeksforgeeks . org/duration-comparetoduration-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-comparetoduration-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的 **compareTo(持续时间)**方法用于将该持续时间与作为参数传递的持续时间进行比较。

**语法:**

```java
public int compareTo(Duration otherDuration)

```

**参数:**该方法接受参数**其他持续时间**，该持续时间将与该持续时间进行比较。

**返回值:**该方法返回一个**整数值**，其中负值表示其他持续时间大于该值，零表示其他持续时间等于该持续时间，正值表示该持续时间大于其他持续时间。

以下示例说明了 Duration.compareTo()方法:

**例 1:**

```java
// Java code to illustrate compareTo() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Duration using ofDays() method
        Duration duration2
            = Duration.ofDays(10);

        // Compare the durations
        // using compareTo() method
        System.out.println(duration1
                               .compareTo(duration2));
    }
}
```

**输出:**

```java
-1

```

**例 2:**

```java
// Java code to illustrate compareTo() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofHours() method
        Duration duration1
            = Duration.ofHours(5);

        // Duration using ofHours() method
        Duration duration2
            = Duration.ofHours(5);

        // Compare the durations
        // using compareTo() method
        System.out.println(duration1
                               .compareTo(duration2));
    }
}
```

**输出:**

```java
0

```

**例 3:**

```java
// Java code to illustrate compareTo() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofDays() method
        Duration duration1
            = Duration.ofDays(5);

        // Duration using ofHours() method
        Duration duration2
            = Duration.ofHours(5);

        // Compare the durations
        // using compareTo() method
        System.out.println(duration1
                               .compareTo(duration2));
    }
}
```

**输出:**

```java
1

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#compareTo-java.time.Duration-)