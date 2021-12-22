# Java 中(int，int，int)方法的日语日期，示例

> 原文:[https://www . geesforgeks . org/japanesedate-of int-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesedate-ofint-int-int-method-in-java-with-example/)

**Java . time . chrono . japanesedate**类的()方法的**用于根据日本日历系统，通过使用传递的前序年、月、日来生成日期。**

**语法:**

```
public static JapaneseDate of(int prolepticYear,
                              int month,
                              int dayOfMonth)

```

**参数**:该方法以以下参数为参数:

*   **年份:**表示日本日期中年份字段的整数值。
*   **月:**表示日本日期中的月字段的整数值。
*   **日:**是日的整数值，表示日本日期中的日字段。

**返回值:**该方法根据日本日历系统，用经过的年月日返回**日期**。

**异常:**如果传递的参数不能形成日期，该方法抛出**日期时间异常**。

以下是举例说明()方法的**:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate of() method

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
            // By using of() method
            JapaneseDate hidate
                = JapaneseDate.of(2008, 04, 24);

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

```
JapaneseDate: Japanese Heisei 20-04-24

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate of() method

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
            // By using of() method
            JapaneseDate hidate
                = JapaneseDate.of(1444, 04, 24);

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

```
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: JapaneseDate before Meiji 6 is not supported

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # of-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#of-int-int-int-)