# Java 中基于时间域的()方法，示例

> 原文:[https://www . geesforgeks . org/chronofield-istimebased-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronofield-istimebased-method-in-java-with-examples/)

**时间域枚举**的 **isTimeBased()** 方法用于检查该时间域是否代表时间的一个组成部分。从纳米秒到一天中的上午-下午的时间场常数是基于时间的。

**语法:**

```
public boolean isTimeBased()

```

**参数:**此方法不接受任何内容。

**返回值:**如果是时间的组成部分，则该方法返回 true。

以下程序说明了基于时间域的()方法:
**程序 1:**

```
// Java program to demonstrate
// ChronoField.isTimeBased() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("HOUR_OF_DAY");

        // apply isTimeBased()
        boolean isTimeBasedAttribute
            = chronoField.isTimeBased();

        // print
        System.out.println(
            "HOUR_OF_DAY"
            + " is Time based attribute:"
            + isTimeBasedAttribute);
    }
}
```

**Output:**

```
HOUR_OF_DAY is Time based attribute:true

```

**程序 2:**

```
// Java program to demonstrate
// ChronoField.isTimeBased() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("YEAR_OF_ERA");

        // apply isTimeBased()
        boolean isTimeBasedAttribute
            = chronoField.isTimeBased();

        // print
        System.out.println("YEAR_OF_ERA"
                           + " is Time based attribute:"
                           + isTimeBasedAttribute);
    }
}
```

**Output:**

```
YEAR_OF_ERA is Time based attribute:false

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronofield . html # isTimeBased()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoField.html#isTimeBased())