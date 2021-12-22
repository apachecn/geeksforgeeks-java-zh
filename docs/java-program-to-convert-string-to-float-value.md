# 将字符串转换为浮点值的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-convert-string-to-float-value/](https://www.geeksforgeeks.org/java-program-to-convert-string-to-float-value/)

在 Java 中给定一个字符串“str”，任务是将这个字符串转换为浮点类型。

**方法:**

这可以通过下面列出的两种方法来完成:

1.  僧曰**解析浮点()凯伊姆**

 **valueOf()方法**

让我们讨论以上两种实现方法的方法，以便更好地理解字符串到浮点值的转换。

**方法 1:** 使用 parseFloat()

float 类中的 ***parseFloat()** 方法* d 是 Java 中的一个内置方法，它返回一个新的 Float，该 Float 被初始化为由指定字符串表示的值，就像 Float 类的 valueOf 方法所做的那样。

**语法:**

```
public static float parseFloat(String s) ;
```

**参数**:它接受一个指定要解析的字符串的强制参数 s。

**返回类型:**返回字符串参数表示的浮点值。

**异常:**

*   Null pointerexception: When the parsed string is null.
*   NumberFormatException: When the parsed string does not contain a resolvable floating-point number.

**例 1**

## 爪哇

```
// Java Program to Convert String to Float Value by
// Implementing parseFloat() method of Float class

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Input string
        String str = "100";

        // Returning the float value
        // represented by the string argument
        float val = Float.parseFloat(str);

        // Prints the float value of the string
        System.out.println("String is converted to float "
                           + val);
    }
}
```

**输出**

```
String is converted to float 100.0
```