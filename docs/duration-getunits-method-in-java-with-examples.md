# Java 中的 Duration getUnits()方法，带示例

> 原文:[https://www . geesforgeks . org/duration-get units-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-getunits-method-in-java-with-examples/)

**java.time 包**中**时长类**的 **getUnits()** 方法，用于获取该时长支持的单位列表。

**语法:**

```java
public List<TemporalUnit> getUnits()

```

**参数:**该方法不接受任何参数。

**返回值:**此方法返回此持续时间支持的**单位列表**。这些是秒表和纳米表。

以下示例说明了 Duration.getUnits()方法:

**例 1:**

```java
// Java code to illustrate getUnits() method

import java.time.Duration;
import java.time.temporal.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P2DT3H4M";

        // Duration using parse() method
        Duration duration
            = Duration.parse(time);

        // Duration using getUnits() method
        List<TemporalUnit>
            listOfUnits = duration.getUnits();

        System.out.println("List of Units: "
                           + listOfUnits);
    }
}
```

**输出:**

```java
List of Units: [Seconds, Nanos]

```

**例 2:**

```java
// Java code to illustrate getUnits() method

import java.time.Duration;
import java.time.temporal.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P1DT4M";

        // Duration using parse() method
        Duration duration
            = Duration.parse(time);

        // Duration using getUnits() method
        List<TemporalUnit>
            listOfUnits = duration.getUnits();

        System.out.println("List of Units: "
                           + listOfUnits);
    }
}
```

**输出:**

```java
List of Units: [Seconds, Nanos]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # getUnits–](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#getUnits--)