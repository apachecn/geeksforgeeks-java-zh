# 时间域是 Java 中基于日期的()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronofield-is dated-based-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronofield-isdatebased-method-in-java-with-examples/)

**时间域枚举**的**是基于日期的()**方法，用于检查该时间域是否代表日期的组成部分。从一周中的某一天到纪元的时间域常数是基于日期的。

**语法:**

```java
public boolean isDateBased()

```

**参数:**此方法不接受任何内容。

**返回值:**如果是日期的组成部分，则该方法返回 true。

下面的程序说明了基于时间域的()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoField.isDateBased() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("HOUR_OF_DAY");

        // apply isDateBased()
        boolean isDateBasedAttribute
            = chronoField.isDateBased();

        // print
        System.out.println(
            "HOUR_OF_DAY"
            + " is Date based attribute:"
            + isDateBasedAttribute);
    }
}
```

**Output:**

```java
HOUR_OF_DAY is Date based attribute:false

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoField.isDateBased() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("YEAR_OF_ERA");

        // apply isDateBased()
        boolean isDateBasedAttribute
            = chronoField.isDateBased();

        // print
        System.out.println("YEAR_OF_ERA"
                           + " is Date based attribute:"
                           + isDateBasedAttribute);
    }
}
```

**Output:**

```java
YEAR_OF_ERA is Date based attribute:true

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronofield . html # isDateBased()](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoField.html#isDateBased())