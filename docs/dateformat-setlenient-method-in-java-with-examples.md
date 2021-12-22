# Java 中的 DateFormat setlained()方法，示例

> 原文:[https://www . geeksforgeeks . org/dateform-set glade-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformat-setlenient-method-in-java-with-examples/)

**日期格式类**中的**设置宽松(布尔宽松)**方法用于指定对该日期格式对象的日期和时间的解释是否宽松。

**语法:**

```java
public void setLenient(boolean leniency)
```

**参数:**该方法采用布尔类型的一个参数，该参数表示日期格式对象的日历模式。布尔值 true 打开宽大处理模式，false 关闭宽大处理模式。

**返回值:**该方法不返回值。

下面的程序说明了日历类的 setlained()方法的工作:
**例 1:**

```java
// Java code to illustrate
// setLenient() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateTimeInstance();
        System.out.println("Object: " + DFormat);

        // String formatting
        String str = DFormat.format(new Date());

        // Displaying the string time
        System.out.println(str);

        System.out.println("Leniency: "
                           + DFormat.isLenient());

        // Changing the leniency
        DFormat.setLenient(false);

        // Displaying the modified leniency
        System.out.println("New Leniency: "
                           + DFormat.isLenient());
    }
}
```

**Output:**

```java
Object: java.text.SimpleDateFormat@7945516e
Mar 28, 2019 6:03:48 PM
Leniency: true
New Leniency: false

```

**例 2:**

```java
// Java code to illustrate
// setLenient() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateInstance();

        System.out.println("Object: " + DFormat);

        // String formatting
        String str = DFormat.format(new Date());

        // Displaying the string time
        System.out.println(str);

        System.out.println("Leniency: "
                           + DFormat.isLenient());

        // Changing the leniency
        DFormat.setLenient(false);

        // Displaying the modified leniency
        System.out.println("New Leniency: "
                           + DFormat.isLenient());
    }
}
```

**Output:**

```java
Object: java.text.SimpleDateFormat@ce9bf0a5
Mar 28, 2019
Leniency: true
New Leniency: false

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/text/dateformat . html # setlained(布尔型)](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#setLenient(boolean))