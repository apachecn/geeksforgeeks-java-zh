# Java 中的 JapaneseDate lengthOfMonth()方法，示例

> 原文:[https://www . geesforgeks . org/japanesedate-length of month-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/japanesedate-lengthofmonth-method-in-java-with-examples/)

**Java . time . chrono . japanesedate**类的 **lengthOfMonth()** 方法用于获取特定日本日期代表的一个月中的天数。

**语法:**

```java
public int lengthOfMonth()

```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法返回特定日本日期代表的一个月中**的天数**。

以下是说明**月长()**方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// lengthOfMonth() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // Getting length of a month
            // by using lengthOfMonth() method
            int length = hidate.lengthOfMonth();

            // Display the result
            System.out.println("no of day present: "
                               + length);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:**

```java
no of day present: 31

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// lengthOfMonth() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.of(2020, 06, 23);

            // Getting length of a month
            // by using lengthOfMonth() method
            int length = hidate.lengthOfMonth();

            // Display the result
            System.out.println(
                "no of day present: "
                + length);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:**

```java
no of day present: 30

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # length of month–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#lengthOfMonth--)