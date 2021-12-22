# Duration 是 Java 中的 Negative()方法，带有示例

> 原文:[https://www . geesforgeks . org/duration-is negative-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-isnegative-method-in-java-with-examples/)

**java.time 包**中**时长类**的**为负()**方法用于检查该时长是否为负。它返回一个描述相同内容的布尔值。

**语法:**

```
public boolean isNegative()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个**布尔值**。如果持续时间为负，则返回真。否则返回假。

以下示例说明了 Duration.isNegative()方法:

**例 1:**

```
// Java code to illustrate isNegative() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P2DT3H4M";

        // Duration using parse() method
        Duration duration = Duration.parse(time);

        // Duration using isNegative() method
        boolean isNegative = duration.isNegative();

        System.out.println(isNegative);
    }
}
```

**输出:**

```
false

```

**例 2:**

```
// Java code to illustrate isNegative() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "-P2DT3H4M";

        // Duration using parse() method
        Duration duration = Duration.parse(time);

        // Duration using isNegative() method
        boolean isNegative = duration.isNegative();

        System.out.println(isNegative);
    }
}
```

**输出:**

```
true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # is negative–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#isNegative--)