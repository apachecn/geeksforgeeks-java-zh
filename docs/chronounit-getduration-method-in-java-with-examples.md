# Java 中的计时单位 getDuration()方法，示例

> 原文:[https://www . geesforgeks . org/chronounit-get duration-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronounit-getduration-method-in-java-with-examples/)

**计时单位枚举**的**获取持续时间()**方法用于返回该计时单位在国际标准化组织日历系统中的估计持续时间。白天因夏令时而异，而月份有不同的长度。

**语法:**

```java
public Duration getDuration()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该单位的**预计持续时间**，不为空。

下面的程序说明了计时单位.获取持续时间()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoUnit.getDuration() method

import java.time.Duration;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("NANOS");

        // apply getDuration()
        Duration getDurationAttribute
            = chronoUnit.getDuration();

        // print
        System.out.println(
            "Duration Estimated :"
            + getDurationAttribute);
    }
}
```

**Output:**

```java
Duration Estimated :PT0.000000001S

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoUnit.getDuration() method

import java.time.Duration;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("DAYS");

        // apply getDuration()
        Duration getDurationAttribute
            = chronoUnit.getDuration();

        // print
        System.out.println(
            "Duration Estimated :"
            + getDurationAttribute);
    }
}
```

**Output:**

```java
Duration Estimated :PT24H

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronounit . html # getDuration()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#getDuration())