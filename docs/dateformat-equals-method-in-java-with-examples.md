# 日期格式等于()Java 中的方法，示例

> 原文:[https://www . geesforgeks . org/dateform-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformat-equals-method-in-java-with-examples/)

**日期格式**类的**等于()**方法用于比较两个日期格式对象。如果此日期格式等于传递的对象，则方法返回真，否则返回假。

**语法:**

```
public boolean equals(Object obj)
```

**参数:**该方法取一个对象类型的参数对象，并引用要与该日期格式对象进行比较的对象。

**返回值:**如果两个对象相等，则该方法返回布尔真，否则该方法返回假。

以下程序说明了日期格式的 equals()方法:
**示例 1:**

```
// Java code to illustrate equals() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        // Initializing the first formatter
        DateFormat DFormat1
            = DateFormat.getDateInstance();

        // Initializing the second formatter
        DateFormat DFormat2
            = DateFormat.getDateInstance();

        // Displaying both the Formats
        Date date = new Date();
        String str_Date1
            = DFormat1.format(date);
        System.out.println("First: "
                           + (str_Date1));

        String str_Date2
            = DFormat2.format(date);
        System.out.println("Second: "
                           + (str_Date2));

        // Comparing both the objects
        System.out.println("Equality: "
                           + DFormat1.equals(DFormat2));
    }
}
```

**Output:**

```
First: Mar 27, 2019
Second: Mar 27, 2019
Equality: true

```

**例 2:**

```
// Java code to illustrate equals() method

import java.text.*;
import java.util.*;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        // Initializing the first formatter
        DateFormat DFormat1
            = DateFormat.getDateInstance();

        // Initializing the second formatter
        DateFormat DFormat2
            = DateFormat.getTimeInstance();

        // Displaying both the Formats
        Date date = new Date();
        String str_Date1
            = DFormat1.format(date);
        System.out.println("First: "
                           + (str_Date1));

        String str_Date2
            = DFormat2.format(date);
        System.out.println("Second: "
                           + (str_Date2));

        // Comparing both the objects
        System.out.println("Equality: "
                           + DFormat1.equals(DFormat2));
    }
}
```

**Output:**

```
First: Mar 27, 2019
Second: 11:04:25 AM
Equality: false

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/text/dateformat . html # equals(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#equals(java.lang.Object))