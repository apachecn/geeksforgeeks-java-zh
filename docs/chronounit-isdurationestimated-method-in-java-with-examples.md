# Java 中的计时单位是指定的估算()方法，示例

> 原文:[https://www . geesforgeks . org/chronounit-is durationestimated-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronounit-isdurationestimated-method-in-java-with-examples/)

**计时单位枚举**的**方法是用来检查计时单位的持续时间是否是一个估计值。该计时单位中的所有时间单位都被认为是准确的，而该计时单位中的所有日期单位都被认为是估计的。**

**语法:**

```
public boolean isDurationEstimated()

```

**参数:**此方法不接受任何内容。

**返回值:**如果估计持续时间，此方法返回**真**，如果准确，返回**假**。

下面的程序说明了计时单位. isDurationEstimated()方法:
**程序 1:**

```
// Java program to demonstrate
// ChronoUnit.isDurationEstimated() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("NANOS");

        // apply isDurationEstimated()
        boolean isDurationEstimatedAttribute
            = chronoUnit.isDurationEstimated();

        // print
        System.out.println(
            "NANOS"
            + " is Duration Estimated attribute:"
            + isDurationEstimatedAttribute);
    }
}
```

**Output:**

```
NANOS is Duration Estimated attribute:false

```

**程序 2:**

```
// Java program to demonstrate
// ChronoUnit.isDurationEstimated() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("DAYS");

        // apply isDurationEstimated()
        boolean isDurationEstimatedAttribute
            = chronoUnit.isDurationEstimated();

        // print
        System.out.println(
            "DAYS"
            + " is Duration Estimated attribute:"
            + isDurationEstimatedAttribute);
    }
}
```

**Output:**

```
DAYS is Duration Estimated attribute:true

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronounit . html # isDurationEstimated()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#isDurationEstimated())