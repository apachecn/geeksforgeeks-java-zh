# Java 控制台 printf(字符串、对象)方法，示例

> 原文:[https://www . geesforgeks . org/console-printfstring-object-method-in-Java-with-examples/](https://www.geeksforgeeks.org/console-printfstring-object-method-in-java-with-examples/)

Java 中**控制台**类的 **printf(String，Object)** 方法用于将格式化的字符串写入控制台的输出流。它使用指定的格式字符串和参数。这是一种方便的方法。

**语法:**

```
public Console printf(String fmt,
                      Object... args)

```

**参数:**该方法接受两个参数:

*   **fmt**–表示字符串的格式。
*   **参数**–它表示字符串格式中由格式说明符引用的参数。

**返回值:**此方法返回控制台。

**异常:**如果字符串格式包含非法语法，或者格式说明符与给定参数不兼容，或者给定格式字符串的参数不足，或者其他条件非法，则此方法抛出 **IllegalFormatException** 。

**注意:** System.console()在联机 IDE 中返回 null。

下面的程序说明了输入输出包中控制台类的 printf(字符串，对象)方法:

**程序 1:**

```
// Java program to illustrate
// Console printf(String, Object) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create the console object
        Console cnsl
            = System.console();

        if (cnsl == null) {
            System.out.println(
                "No console available");
            return;
        }

        String fmt = "%1$4s %2$10s %3$10s%n";

        cnsl.printf(fmt, "Books", "Author", "Price");
        cnsl.printf(fmt, "-----", "------", "-----");
        cnsl.printf(fmt, "DBMS", "Navathe", "800");
        cnsl.printf(fmt, "Algorithm", "Cormen", "925");
        cnsl.printf(fmt, "Operating System", "Rajib Mall", "750");
    }
}
```

**Output:**![](img/31c82c6126fdc40240b01e67809d53b0.png)

**程序 2:**

```
// Java program to illustrate
// Console printf(String, Object) method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {
        // Create the console object
        Console cnsl
            = System.console();

        if (cnsl == null) {
            System.out.println(
                "No console available");
            return;
        }

        String fmt = "%1$4s %2$10s %3$10s%n";

        cnsl.printf(fmt, "Items", "Quantity", "Price");
        cnsl.printf(fmt, "-----", "------", "-----");
        cnsl.printf(fmt, "Tomato", "1 Kg", "80");
        cnsl.printf(fmt, "Apple", "3 Kg", "500");
        cnsl.printf(fmt, "Potato", "2 Kg", "75");
    }
}
```

**Output:**![](img/04af0b952d06c0123ac01a0bbabe8b7c.png)

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/console . html # printf(Java . lang . string，java.lang.Object…)](https://docs.oracle.com/javase/10/docs/api/java/io/Console.html#printf(java.lang.String, java.lang.Object...))