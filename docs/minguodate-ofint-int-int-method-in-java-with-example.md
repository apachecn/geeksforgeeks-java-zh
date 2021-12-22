# Java 中(int，int，int)方法的 MinguoDate，示例

> 原文:[https://www . geeksforgeeks . org/mingodate-of int-int-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-ofint-int-int-method-in-java-with-example/)

**Java . time . chrono . mingodate**类的()方法的**用于根据民国历法系统，利用经过的前序年、月、日生成日期。**

**语法:**

```java
public static MinguoDate of(int Year,
            int month, int dayOfMonth)

```

**参数**:该方法以以下参数为参数:

*   **年份:**表示民国日期中年份字段的整数值。
*   **月:**表示民国日期中的月字段的整数值。
*   **日:**表示民国日的日字段的整数值。

**返回值:**该方法根据民国历法系统，用经过的年月日返回**日期**。

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
            // MinguoDate Object
            // By using of() method
            MinguoDate hidate
                = MinguoDate.of(1444, 04, 24);

            // Display the result
            System.out.println("MinguoDate: "
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
MinguoDate: Minguo ROC 1444-04-24

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
            // MinguoDate Object
            // By using of() method
            MinguoDate hidate
                = MinguoDate.of(1911, 04, -24);

            // Display the result
            System.out.println("MinguoDate: "
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
Exception thrown:
 java.time.DateTimeException:
 Invalid value for DayOfMonth (valid values 1 - 28/31): -24

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # of-int-int-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#of-int-int-int-)