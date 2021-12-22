# Java 中的 DateFormat getDateInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/dateform-getdateinstance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformat-getdateinstance-method-in-java-with-examples/)

Java 中 **DateFormat 类**的 **getDateInstance()** 方法用于获取日期格式化程序。此日期格式化程序带有默认区域设置的默认格式样式。

**语法:**

```
public static final DateFormat getDateInstance()
```

**参数:**该方法不取任何参数。

**返回值:**该方法以特定格式返回一个日期格式化程序。

下面的程序说明了 getDateInstance()方法在 Java 中的使用:
**示例 1:**

```
// Java code to illustrate
// getDateInstance() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] argv)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateInstance();
        System.out.println("Object: " + DFormat);

        // String formatting
        String str = DFormat.format(new Date());

        // Displaying the string date
        System.out.println(str);
    }
}
```

**Output:**

```
Object: java.text.SimpleDateFormat@ce9bf0a5
Mar 27, 2019

```

**例 2:**

```
// Java code to illustrate
// getDateInstance() method

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

        // Initializing the Date formatter
        DateFormat DFormat
            = DateFormat.getDateInstance();
        System.out.println("Object: " + DFormat);

        // String formatting
        String str = DFormat.format(new Date());

        // Displaying the string date
        System.out.println(str);
    }
}
```

**Output:**

```
The Original: 03/27/2019
Object: java.text.SimpleDateFormat@ce9bf0a5
Mar 27, 2019

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/text/dateformat . html # getdate instance()](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#getDateInstance())