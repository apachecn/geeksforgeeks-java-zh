# Java 中(JapaneseEra，int，int，int)方法的日语日期，示例

> 原文:[https://www . geesforgeks . org/japanesedate-japanesereint-int-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesedate-ofjapaneseeraint-int-int-method-in-java-with-example/)

**Java . time . chrono . japanesedate**类的()方法的**用于根据日本日历系统，使用经过的前序年、月、日、日生成日期。**

**语法:**

```java
public static JapaneseDate of(JapaneseEra era,
                              int yearOfEra,
                              int month,
                              int dayOfMonth)

```

**参数**:该方法以以下参数为参数:

*   **时代:**日本时代的客体，代表日本日期中的时代场。
*   **年份:**表示日本日期中年份字段的整数值。
*   **月:**表示日本日期中的月字段的整数值。
*   **日:**是日的整数值，表示日本日期中的日字段。

**返回值:**该方法根据日本历法系统，通过使用经过的无序年、月、日、纪元，返回**日期**。

**异常:**如果传递的参数不能形成日期，该方法抛出**日期时间异常**。

以下是举例说明()方法的**:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
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
                = JapaneseDate.of(
                    JapaneseEra.HEISEI,
                    2008, 04, 24);

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
JapaneseDate: Japanese Heisei 2008-04-24

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
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
                = JapaneseDate.of(
                    JapaneseEra.TAISHO,
                    2008, 04, 24);

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
passed parameter can not form a date
Exception thrown: java.time.DateTimeException: year, month, and day not valid for Era

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # of-Java . time . chrono . japanesera-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#of-java.time.chrono.JapaneseEra-int-int-int-)