# Java 中的 LocalDate getLong()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-getlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-getlong-method-in-java-with-examples/)

Java 中 LocalDate 类的 getLong()方法得到了在这个日期适用的纪元。

**语法** :

```java
public long getLong(TemporalField field)

```

**参数**:该方法接受单个强制参数*字段*，指定要获取的字段，不为空。

**返回值**:该函数返回该字段的值。

**异常**:程序抛出三个异常，描述如下:

1.  **[Date and Time Exception]** : If the value of this field cannot be obtained or the value is beyond the valid range of this field, an exception will be thrown.
2.  **Unsupported Temporaltypeexception** : If this field is not supported or the range of values exceeds a long integer, it will be thrown.
3.  **Arithmetic exception** : thrown when numerical value overflows.

下面的程序说明了 Java 中 LocalDate 的 **getLong()** 方法:

**程序 1** :

```java
// Program to illustrate the getLong() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getLong(ChronoField.DAY_OF_MONTH));
    }
}
```

**输出:**

```java
27

```

**程序二** :

```java
// Program to illustrate the getLong() method

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getLong(ChronoField.DAY_OF_YEAR));
    }
}
```

**输出:**

```java
331

```

**程序 3** :

```java
// Program to illustrate the getLong() method
// Exception Program

import java.util.*;
import java.time.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        try {
            LocalDate dt = LocalDate.parse("2017-01-32");
            System.out.println(dt.getLong(ChronoField.DAY_OF_MONTH));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.time.format.DateTimeParseException: Text '2017-01-32' could not be parsed: Invalid value for DayOfMonth (valid values 1 - 28/31): 32

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # getLong(Java . time . temporal field)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getLong(java.time.temporal.TemporalField))