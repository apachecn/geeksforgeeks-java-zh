# Java 中的 ChronoLocalDate get()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-get-method-in-java-with-examples/)

Java 方法中**chronolocalydate**接口的 **get()** 方法从该日期获取指定字段的值作为 int。

**语法**:

```java
public int get(TemporalField field)

```

**参数**:该方法接受一个参数*字段*，该字段是要获取的字段，不需要为空。

**返回值**:返回该字段的值。

**异常**:函数抛出如下三个异常:

*   **DateTimeException** :如果无法获取字段的值或者该值超出了字段的有效值范围，则会引发此异常。
*   **unsupportedtemporaltypexception**:如果字段不受支持或者值的范围超过一个整数，将引发此异常
*   **算术异常**:如果出现数值溢出，则抛出该异常

下面的程序举例说明了 Java 中的 **get()** 方法
程序 1 :

```java
// Program to illustrate the get() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {

        ChronoLocalDate dt
            = LocalDate.parse("2017-02-16");
        System.out.println(dt.get(
            ChronoField.MONTH_OF_YEAR));
    }
}
```

**Output:**

```java
2

```

**程序 2** :

```java
// Program to illustrate the get() method
// Exception Program

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.ChronoField;

public class GfG {
    public static void main(String[] args)
    {
        try {
            ChronoLocalDate dt
                = LocalDate.parse("2017-02-30");
            System.out.println(dt.get(
                ChronoField.MONTH_OF_YEAR));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.time.format.DateTimeParseException: 
 Text '2017-02-30' could not be parsed: 
 Invalid date 'FEBRUARY 30'

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/temporal/temporalacessor . html # get-Java . time . temporal field-](https://docs.oracle.com/javase/9/docs/api/java/time/temporal/TemporalAccessor.html#get-java.time.temporal.TemporalField-)