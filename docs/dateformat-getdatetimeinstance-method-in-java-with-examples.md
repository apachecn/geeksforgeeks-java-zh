# Java 中的日期格式 getDateTimeInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/dateform-getdatetime instance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformat-getdatetimeinstance-method-in-java-with-examples/)

Java 中 **DateFormat 类**的 **getDateTimeInstance()** 方法用于获取日期/时间格式化程序。此日期/时间格式化程序带有默认区域设置的默认格式样式。

**语法:**

```java
public static final DateFormat getDateTimeInstance()
```

**参数:**该方法不取任何参数。

**返回值:**该方法以特定格式返回日期/时间格式化程序。

下面的程序说明了 getDateTimeInstance()方法在 Java 中的使用:
**示例 1:**

```java
// Java code to illustrate
// getDateTimeInstance() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] argv)
    {

        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateTimeInstance();
        System.out.println("Object: " + DFormat);

        // String formatting
        String str = DFormat.format(new Date());

        // Displaying the string time
        System.out.println(str);
    }
}
```

**Output:**

```java
Object: java.text.SimpleDateFormat@7945516e
Mar 28, 2019 4:03:11 AM

```

**例 2:**

```java
// Java code to illustrate
// getDateTimeInstance() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] args)
        throws InterruptedException
    {

        // Initializing SimpleDateFormat
        SimpleDateFormat SDFormat
            = new SimpleDateFormat(
                "MM/dd/yyyy");

        // Displaying the formats
        Date date = new Date();
        String str_Date1
            = SDFormat.format(date);
        System.out.println("The Original: "
                           + (str_Date1));

        // Initializing the Time formatter
        DateFormat DFormat
            = DateFormat.getDateTimeInstance();
        System.out.println("Object: " + DFormat);

        // String formatting
        String str = DFormat.format(new Date());

        // Displaying the string time
        System.out.println(str);
    }
}
```

**Output:**

```java
The Original: 03/28/2019
Object: java.text.SimpleDateFormat@7945516e
Mar 28, 2019 4:03:13 AM

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/text/date format . html # getdate time instance()](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#getDateTimeInstance())