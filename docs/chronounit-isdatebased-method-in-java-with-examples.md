# 计时单位是 Java 中基于日期的()方法，示例

> 原文:[https://www . geesforgeks . org/chronounit-is dates-based-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronounit-isdatebased-method-in-java-with-examples/)

**计时单位枚举**的**是基于日期的()**方法，用于检查该计时单位是否为日期单位。从天到纪元的所有时间单位都是基于日期的。

**语法:**

```
public boolean isDateBased()

```

**参数:**此方法不接受任何内容。

**返回值:**如果是日期单位，则该方法返回**真**，如果是时间单位，则返回**假**。

下面的程序说明了计时单位的方法:
**程序 1:**

```
// Java program to demonstrate
// ChronoUnit.isDateBased() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("DECADES");

        // apply isDateBased()
        boolean isDateBasedAttribute
            = chronoUnit.isDateBased();

        // print
        System.out.println(
            "DECADES"
            + " is Date based attribute:"
            + isDateBasedAttribute);
    }
}
```

**Output:**

```
DECADES is Date based attribute:true

```

**程序 2:**

```
// Java program to demonstrate
// ChronoUnit.isDateBased() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("MINUTES");

        // apply isDateBased()
        boolean isDateBasedAttribute
            = chronoUnit.isDateBased();

        // print
        System.out.println(
            "MINUTES"
            + " is Date based attribute:"
            + isDateBasedAttribute);
    }
}
```

**Output:**

```
MINUTES is Date based attribute:false

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronounit . html # isDateBased()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#isDateBased())