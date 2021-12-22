# Java 中的 ChronoLocalDateTime get()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-get-method-in-java-with-examples/)

Java 中**ChronalDateTiME**类的 **get()** 方法用于从该 ChronalDateTiME 中获取作为输入传递的指定字段的值作为整数。此方法在此 ChronoLocalDateTime 中查询该字段的值，返回值将始终在该字段的有效值范围内。当字段不受支持并且方法无法返回 int 值时，将引发异常。

**语法:**

```java
default int get(TemporalField field)

```

**参数:**该方法接受单个参数**字段**，代表要获取的字段。

**返回值:**该方法为该字段返回一个 **int** 值。

**异常:**该方法抛出以下异常:

*   **日期时间异常**:如果无法获取字段的值或者该值超出了字段有效值的范围。
*   **unsupportedtemporaltypexception**:如果不支持该字段或者值的范围超过了一个整数。
*   **算术异常**:如果出现数值溢出。

下面的程序说明了 get()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.get() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDateTime object
        ChronoLocalDateTime localDT
            = LocalDateTime
                  .parse("2019-12-31T19:15:30");

        // apply get() method
        int result
            = localDT.get(ChronoField.NANO_OF_SECOND);

        // print result
        System.out.println("Value: "
                           + result);
    }
}
```

**Output:**

```java
Value: 0

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoLocalDateTime.get() method

import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoLocalDateTime object
        ChronoLocalDateTime localDT
            = LocalDateTime
                  .parse("2018-10-25T23:12:31.123");

        // apply get() method
        int result
            = localDT.get(ChronoField.MILLI_OF_SECOND);

        // print result
        System.out.println("Value: "
                           + result);
    }
}
```

**Output:**

```java
Value: 123

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/temporal/temporalacessor . html # get-Java . time . temporal field-](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#get-java.time.temporal.TemporalField-)