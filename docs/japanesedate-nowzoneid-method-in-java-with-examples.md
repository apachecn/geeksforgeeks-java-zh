# Java 中的 JapaneseDate now(ZoneId)方法，示例

> 原文:[https://www . geesforgeks . org/japanesedate-now zoneid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/japanesedate-nowzoneid-method-in-java-with-examples/)

**Java . time . chrono . japanesedate**类的 **now()** 方法用于根据指定区域的日本日历系统获取当前的日本日期。

**语法:**

```java
public static JapaneseDate now(ZoneId zone)

```

**参数**:该方法以**区域 id** 为对象，在此基础上形成日本日期。

**返回值:**此方法从指定的时钟根据日本日历系统返回当前的**日本日期**。

以下是举例说明**现在()**方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate now() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing ZoneId
            ZoneId id = ZoneId.systemDefault();

            // Creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now(id);

            // Display the result
            System.out.println("JapaneseDate: "
                               + hidate);
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
JapaneseDate: Japanese Heisei 32-03-23

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate now() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {

            // Creating and initializing ZoneId
            ZoneId id = ZoneId.of("Z");

            // Creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now(id);

            // Display the result
            System.out.println("JapaneseDate: "
                               + hidate);
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
JapaneseDate: Japanese Heisei 32-03-23

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # now-Java . time . zoneid-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#now-java.time.ZoneId-)