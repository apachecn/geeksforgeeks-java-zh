# Java 中(int，int，int)方法的 HijrahDate，示例

> 原文:[https://www . geesforgeks . org/hijrahdate-of int-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahdate-ofint-int-int-method-in-java-with-example/)

**Java . time . chrono . hijrahdate**类的()方法的**用于根据伊斯兰回历系统，利用传递的公历年、月、日生成日期。**

**语法:**

```
public static HijrahDate of(int Year,
            int month, int dayOfMonth)

```

**参数**:该方法以以下参数为参数:

*   **年份:**表示回历日期中年份字段的整数值。
*   **月:**表示 hijrah date 中的月字段的整数值。
*   **day:** 是日的整数值，代表 hijrah date 中的日字段。

**返回值:**该方法根据伊斯兰回历系统，用经过的前一年、月、日返回**日期**。

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
            // HijrahDate Object
            // By using of() method
            HijrahDate hidate
                = HijrahDate.of(1444, 04, 24);

            // Display the result
            System.out.println("HijrahDate: "
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
HijrahDate: Hijrah-umalqura AH 1444-04-24

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
            // HijrahDate Object
            // By using of() method
            HijrahDate hidate
                = HijrahDate.of(2014, 04, 24);

            // Display the result
            System.out.println("HijrahDate: "
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
Exception thrown: java.time.DateTimeException:
                  Invalid Hijrah date,
                  year: 2014, month: 4

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrahdate . html # of-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#of-int-int-int-)