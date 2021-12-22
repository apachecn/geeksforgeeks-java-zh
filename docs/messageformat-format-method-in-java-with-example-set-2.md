# Java 中的 MessageFormat format()方法，示例:Set–2

> 原文:[https://www . geesforgeks . org/message format-format-method-in-Java-with-example-set-2/](https://www.geeksforgeeks.org/messageformat-format-method-in-java-with-example-set-2/)

**java.text.MessageFormat** 类的 **format()** 方法用于根据消息格式对象的指定模式获取对象的格式化数组。执行操作时将考虑新的字符串模式。

**语法:**

```java
public static String format(String pattern,
                            Object... arguments)
```

**参数**:该方法以下列参数为参数。

*   **模式:**–字符串模式，根据该模式将格式化对象数组
*   **参数:-** 要进行格式化的对象数组。

**返回值:**该方法返回字符串值，该值将具有字符串形式的格式化对象数组。

**异常:**如果模式为空，该方法抛出**空指针异常**。

以下是说明**格式()**方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// format() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing new MessageFormat Object
            MessageFormat mf
                = new MessageFormat("{0, number, #}, {0, number, #.##}, {0, number}");

            // Creating and initializing an array of type Double
            // to be formatted
            Object[] objs = { new Double(4.234567) };

            // Formatting an array of object
            // using format() method
            String str = mf.format("{0, number, #.#}", objs);

            // display the result
            System.out.println("formatted array : "
                               + str);
        }
        catch (NullPointerException e) {
            System.out.println("pattern is null " + e);
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
formatted array : 4.2

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// format() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing new MessageFormat Object
            MessageFormat mf
                = new MessageFormat("{0, number, #}, {0, number, #.##}, {0, number}");

            // Creating and initializing an array of type Double
            // to be formatted
            Object[] objs = { new Double(4.234567) };

            // Formatting an array of object
            // using format() method
            String str = mf.format(null, objs);

            // display the result
            System.out.println("formatted array : "
                               + str);
        }
        catch (NullPointerException e) {
            System.out.println("pattern is null ");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
pattern is null 
Exception thrown : java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # format-Java . lang . string-Java . lang . object……-](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#format-java.lang.String-java.lang.Object...-)