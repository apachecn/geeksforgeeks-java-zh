# Java 中的 LocalDate isSupported()方法，示例

> 原文:[https://www . geesforgeks . org/local date-issupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-issupported-method-in-java-with-examples/)

在 LocalDate 类中，根据传递给它的参数，有两种类型的 isSupported()方法。

### 问题支持(临时字段)

**isSupported()** 一个 **LocalDate** 类的方法，用来检查指定的字段是否被 LocalDate 类支持，也就是说使用这个方法我们可以检查这个 LocalDate 是否可以查询到指定的字段。

计时字段支持的字段有:

*   对齐 _ 周 _ 年

所有其他时间域实例都将返回 false。

**语法:**

```
public boolean isSupported(TemporalField field)

```

**参数:**此方法接受一个单参数**字段**，即要检查的字段。

**返回值:**如果该区域日期支持该字段，则该方法返回**布尔值【true，否则返回 false。**

下面的程序说明了 isSupported()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDate.isSupported() method

import java.time.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate lt
            = LocalDate.parse("2018-11-03");

        // check YEAR_OF_ERA is supported in LocalDate
        boolean value
            = lt.isSupported(ChronoField.YEAR_OF_ERA);

        // print result
        System.out.println("YEAR_OF_ERA Field is supported: "
                           + value);
    }
}
```

**输出:**

```
YEAR_OF_ERA Field is supported: true

```

### 发行支持(临时单位)

**一个 **LocalDate** 类的 isSupported()** 方法用来检查指定的单位是否被 LocalDate 类支持意味着使用这个方法我们可以检查这个 LocalDate 是否可以查询到指定的单位。

计时单位支持的字段有:

*   天
*   周；星期
*   月份
*   年
*   数十年
*   世纪
*   一千年
*   年代

所有其他计时单位实例将返回 false。

**语法:**

```
public boolean isSupported(TemporalUnit unit)

```

**参数:**该方法只接受一个参数**单位**，即要检查的单位。

**返回值:**如果该区域日期支持该字段，则该方法返回**布尔值【true，否则返回 false。**

下面的程序说明了 isSupported()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDate.isSupported() method

import java.time.*;
import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate lt
            = LocalDate.parse("2018-12-29");

        // check CENTURIES ChronoUnit supported in LocalDate
        boolean value
            = lt.isSupported(ChronoUnit.CENTURIES);

        // print result
        System.out.println("ChronoUnit CENTURIES is  supported: "
                           + value);
    }
}
```

**输出:**

```
ChronoUnit CENTURIES is  supported: true

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # isSupported(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isSupported(java.time.temporal.TemporalField))[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # isSupported(Java . time . temporal nit)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#isSupported(java.time.temporal.TemporalUnit))