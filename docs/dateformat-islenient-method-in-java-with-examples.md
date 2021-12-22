# Java 中的 DateFormat isLenient()方法，带示例

> 原文:[https://www . geesforgeks . org/dateform-islenient-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformat-islenient-method-in-java-with-examples/)

DateFormat 类中的 **isLenient()** 方法用于了解和理解这个 DateFormat 对象的日期和时间的解析是否被认为宽松。

**语法:**

```java
public boolean isLenient()
```

**参数:**该方法不取任何参数。

**返回值:**如果对此日历的解释宽松，则该方法返回真，否则返回假。

下面的程序说明了日历类的 isLenient()方法的工作:
**例 1:**

```java
// Java code to illustrate
// isLenient() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateTimeInstance();
        System.out.println("Object: "
                           + DFormat);

        // String formatting
        String str
            = DFormat.format(new Date());

        // Displaying the string time
        System.out.println(str);

        System.out.println("Leniency: "
                           + DFormat.isLenient());
    }
}
```

**Output:**

```java
Object: java.text.SimpleDateFormat@7945516e
Mar 28, 2019 4:23:01 AM
Leniency: true

```

**例 2:**

```java
// Java code to illustrate
// isLenient() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] argv)
    {
        // Initializing the first formatter
        DateFormat DFormat
            = DateFormat.getDateInstance();
        System.out.println("Object: "
                           + DFormat);

        // String formatting
        String str
            = DFormat.format(new Date());

        // Displaying the string time
        System.out.println(str);

        System.out.println("Leniency: "
                           + DFormat.isLenient());
    }
}
```

**Output:**

```java
Object: java.text.SimpleDateFormat@ce9bf0a5
Mar 28, 2019
Leniency: true

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/text/dateformat . html # isLenient()](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#isLenient())