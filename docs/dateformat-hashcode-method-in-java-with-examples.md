# Java 中的 DateFormat hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/dateform-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformat-hashcode-method-in-java-with-examples/)

**日期格式类**的 **hashCode()** 方法用于返回该日期格式对象的哈希码值。哈希代码是整数类型。

**语法:**

```java
public int hashCode()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回该 DateFormat 对象的哈希码值，并且是整数类型。

以下程序说明了 hashCode()方法的工作日期格式:
**示例 1:**

```java
// Java to illustrate hashCode() method

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
        String str_Date1 = DFormat.format(date);
        System.out.println("The Original: "
                           + (str_Date1));

        // Displaying the hash code
        System.out.println("The hash code: "
                           + DFormat.hashCode());
    }
}
```

**Output:**

```java
The Original: Mar 27, 2019 10:20:51 AM
The hash code: 2034585966

```

**例 2:**

```java
// Java to illustrate hashCode() method

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
        String str_Date1 = DFormat.format(date);
        System.out.println("The Original: "
                           + (str_Date1));

        // Displaying the hash code
        System.out.println("The hash code: "
                           + DFormat.hashCode());
    }
}
```

**Output:**

```java
The Original: 03/27/2019
The hash code: 2087096576

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/text/dateformat . html # hashCode()](https://docs.oracle.com/javase/7/docs/api/java/text/DateFormat.html#hashCode())