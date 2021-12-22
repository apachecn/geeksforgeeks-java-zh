# Java 中的计时单位值()方法，示例

> 原文:[https://www . geesforgeks . org/chronounit-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronounit-values-method-in-java-with-examples/)

**计时单位枚举**的**值()**方法用于包含该计时单位单位的数组，按顺序声明。

**语法:**

```java
public static ChronoUnit[] values()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个包含这个枚举类型的常量的**数组**，按照它们被声明的顺序。

以下程序说明了计时单位值()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoUnit.values() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronounit
            = ChronoUnit.valueOf("FOREVER");

        // apply values()
        ChronoUnit[] array
            = chronounit.values();

        // print
        for (int i = 0; i < array.length; i++)
            System.out.println(array[i]);
    }
}
```

**Output:**

```java
Nanos
Micros
Millis
Seconds
Minutes
Hours
HalfDays
Days
Weeks
Months
Years
Decades
Centuries
Millennia
Eras
Forever

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoUnit.values() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronounit
            = ChronoUnit.valueOf("CENTURIES");

        // apply values()
        ChronoUnit[] array
            = chronounit.values();

        // print
        System.out.println("ChronoUnit length:"
                           + array.length);
    }
}
```

**Output:**

```java
ChronoUnit length:16

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronounit . html # values()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#values())