# Java 中的 ChronoField valueOf()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronofield-value of-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronofield-valueof-method-in-java-with-examples/)

**时间域枚举**的 **valueOf()** 方法用于返回指定名称的该类型的枚举常量。

**语法:**

```
public static ChronoField valueOf(String name)

```

**参数:**该方法接受**名称**，这是要返回的枚举常量的名称。

**返回值:**该方法返回指定名称的枚举常量。

以下程序说明了计时场.值 Of()方法:
**程序 1:**

```
// Java program to demonstrate
// ChronoField.valueOf() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("HOUR_OF_DAY");

        // print
        System.out.println("ENUM: "
                           + chronoField);
    }
}
```

**Output:**

```
ENUM: HourOfDay

```

**程序 2:**

```
// Java program to demonstrate
// ChronoField.valueOf() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("YEAR_OF_ERA");

        // print
        System.out.println("ENUM: "
                           + chronoField);
    }
}
```

**Output:**

```
ENUM: YearOfEra

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronofield . html # value of(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoField.html#valueOf(java.lang.String))