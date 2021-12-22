# Java 中的 ChronoLocalDate 格式()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-format-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-format-method-in-java-with-examples/)

Java 方法中**ChronalDate**接口的 **format()** 方法使用指定的格式化程序格式化该日期。

**语法** :

```java
public String format(DateTimeFormatter formatter)

```

**参数**:这个方法接受一个参数 *obj* ，指定要使用的格式化程序，并且不为空。

**异常**:该函数只抛出打印错误时出现的*日期时间异常*。

**返回值**:返回格式化的日期字符串，不为空。

下面的程序说明了 Java 中的**格式()**方法:

**程序 1** :

```java
// Program to illustrate the format() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {

        // Parses the date
        ChronoLocalDate dt
            = LocalDate.parse("2018-11-01");
        System.out.println(dt);

        // Function call
        DateTimeFormatter formatter
            = DateTimeFormatter
                  .ofPattern("dd/MM/YYYY");

        System.out.println(formatter.format(dt));
    }
}
```

**输出:**

```java
2018-11-01
01/11/2018

```

**程序二**:举例说明异常。

```java
// Program to illustrate the format() method
// Exception Program

import java.util.*;
import java.time.*;
import java.time.chrono.*;
import java.time.format.DateTimeFormatter;

public class GfG {
    public static void main(String[] args)
    {
        try {
            // Parses the date
            ChronoLocalDate dt
                = LocalDate.parse("2018-01-32");
            System.out.println(dt);

            // Function call
            DateTimeFormatter formatter
                = DateTimeFormatter
                      .ofPattern("dd/MM/YYYY");

            System.out.println(formatter.format(dt));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.time.format.DateTimeParseException: 
 Text '2018-01-32' could not be parsed:
 Invalid value for DayOfMonth (valid values 1 - 28/31): 32

```

**参考**:[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/chronolocaldata . html # format-Java . time . format . datetimeformatter-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#format-java.time.format.DateTimeFormatter-)