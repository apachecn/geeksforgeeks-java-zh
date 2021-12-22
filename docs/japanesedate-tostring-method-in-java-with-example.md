# Java 中的日本日期字符串()方法，示例

> 原文:[https://www . geesforgeks . org/japanesedate-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesedate-tostring-method-in-java-with-example/)

**Java . time . chrono . japanesedate**类的 **toString()** 方法用于将日语日期表示为字符串格式。

**语法:**

```
public String toString()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法将**日本日期**返回为字符串格式。

以下是说明 **toString()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method

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
            JapaneseDate hidate = JapaneseDate.now();

            // Getting string represntation
            // of Japanese date
            // by using toString() method
            String date = hidate.toString();

            // Display the result
            System.out.println("Japanesedate : "
                               + date);
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

```
Japanesedate : Japanese Heisei 32-04-13

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method

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
                = JapaneseDate.of(2008, 05, 23);

            // Getting string represntation
            // of Japanese date
            // by using toString() method
            String date = hidate.toString();

            // Display the result
            System.out.println("Japanesedate : "
                               + date);
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

```
Japanesedate : Japanese Heisei 20-05-23

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#toString--)