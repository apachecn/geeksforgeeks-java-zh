# Java 中的 Duration toString()方法，示例

> 原文:[https://www . geesforgeks . org/duration-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-tostring-method-in-java-with-examples/)

**java.time 包**中**时长类**的 **toString()** 方法用于获取该时长的字符串值。该字符串采用国际标准化组织 8601 格式。

**语法:**

```
public String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个**字符串值**，这是这个持续时间的字符串值。

以下示例说明了 Duration.toString()方法:

**例 1:**

```
// Java code to illustrate toString() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using parse() method
        Duration duration
            = Duration.parse("P2DT3H4M");

        // Get the String value
        // using toString() method
        System.out.println(duration1.toString());
    }
}
```

**例 2:**

```
// Java code to illustrate toString() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofHours() method
        Duration duration
            = Duration.ofHours(5);

        // Get the String value
        // using toString() method
        System.out.println(duration1.toString());
    }
}
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#toString--)