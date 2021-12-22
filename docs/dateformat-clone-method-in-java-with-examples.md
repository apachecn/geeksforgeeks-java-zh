# Java 中的 DateFormat clone()方法，示例

> 原文:[https://www . geesforgeks . org/dateform-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformat-clone-method-in-java-with-examples/)

**日期格式类**的**克隆()**方法用于创建该日期格式的副本。它会创建此日期格式的另一个副本。

**语法:**

```java
public Object clone()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回日期格式的副本。

下面的程序说明了克隆()的工作方法日期格式:
**示例 1:**

```java
// Java to illustrate clone() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        // Initializing DateFormat
        DateFormat DFormat
            = DateFormat.getDateTimeInstance();

        // Displaying the formats
        Date date = new Date();
        String str_Date1
            = DFormat.format(date);
        System.out.println("The Original: "
                           + (str_Date1));

        // Using clone()
        System.out.println("Is the clone equal? "
                           + DFormat.clone()
                                 .equals(DFormat));
    }
}
```

**Output:**

```java
The Original: Mar 27, 2019 10:09:48 AM
Is the clone equal? true

```

**例 2:**

```java
// Java to illustrate clone() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        // Initializing DateFormat
        DateFormat DFormat
            = new SimpleDateFormat("MM/dd/yyyy");

        // Displaying the formats
        Date date = new Date();
        String str_Date1
            = DFormat.format(date);
        System.out.println("The Original: "
                           + (str_Date1));

        // Using clone()
        System.out.println("Is the clone equal? "
                           + DFormat.clone()
                                 .equals(DFormat));
    }
}
```

**Output:**

```java
The Original: 03/27/2019
Is the clone equal? true

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/text/dateformat . html # clone()](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#clone())