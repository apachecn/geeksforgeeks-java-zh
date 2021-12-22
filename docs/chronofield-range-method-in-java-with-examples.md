# Java 中的计时范围()方法，示例

> 原文:[https://www . geesforgeks . org/chronofield-range-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronofield-range-method-in-java-with-examples/)

**计时场枚举**的**范围()**方法用于返回计时场常数的有效值范围。该范围内的所有字段都可以表示为长整数。

**语法:**

```java
public ValueRange range()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回字段的有效值范围，不为空。

下面的程序说明了时空范围()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoField.range() method

import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("HOUR_OF_DAY");

        // apply range()
        ValueRange rangeAttribute
            = chronoField.range();

        // print
        System.out.println("ValueRange for HOUR_OF_DAY"
                           + " is :"
                           + rangeAttribute);
    }
}
```

**Output:**

```java
ValueRange for HOUR_OF_DAY is :0 - 23

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoField.range() method

import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("YEAR_OF_ERA");

        // apply range()
        ValueRange rangeAttribute
            = chronoField.range();

        // print
        System.out.println("ValueRange for YEAR_OF_ERA"
                           + " is:"
                           + rangeAttribute);
    }
}
```

**Output:**

```java
ValueRange for YEAR_OF_ERA is:1 - 999999999/1000000000

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronofield . html # range()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoField.html#range())