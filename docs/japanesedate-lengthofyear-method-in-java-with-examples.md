# Java 中的 JapaneseDate lengthOfYear()方法，示例

> 原文:[https://www . geesforgeks . org/japanesedate-length of year-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/japanesedate-lengthofyear-method-in-java-with-examples/)

**Java . time . chrono . japanesedate**类的 **lengthOfYear()** 方法用于获取特定日本日期所代表的一年中的天数。

**语法:**

```java
public int lengthOfYear()

```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法返回一年中由特定日本日期表示的整数形式的**天数**。

下面举例说明 **lengthOfYear()** 方法:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// lengthOfYear() method

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
            // japaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.of(2006, 06, 23);

            // Getting length of a year
            // by using lengthOfYear() method
            int length = hidate.lengthOfYear();

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
no of day present: 365

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// lengthOfYear() method

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
            // japaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // Getting length of a year
            // by using lengthOfYear() method
            int length = hidate.lengthOfYear();

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
no of day present: 366

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # length of year–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#lengthOfYear--)