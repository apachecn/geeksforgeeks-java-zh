# Java 中的 Duration getNano()方法，带示例

> 原文:[https://www . geesforgeks . org/duration-getnano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-getnano-method-in-java-with-examples/)

使用 **java.time 包**中**时长类**的 **getNano()** 方法获取该时长的 Nano 值。

**语法:**

```
public long getNano()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回这个持续时间的纳米的一个**长值**。

以下示例说明了 Duration.getNano()方法:

**例 1:**

```
// Java code to illustrate getNano() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P2DT3H4M";

        // Duration using parse() method
        Duration duration = Duration.parse(time);

        // Get the duration in nanos
        // using getNano() method
        System.out.println(duration.getNano());
    }
}
```

**输出:**

```
0

```

**例 2:**

```
// Java code to illustrate getNano() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration using ofHours() method
        Duration duration = Duration.ofHours(5);

        // Get the duration in nanos
        // using getNano() method
        System.out.println(duration.getNano());
    }
}
```

**输出:**

```
0

```

**参考:** [甲骨文文档](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#getNano--)