# Java 程序打印 ASCII 值

> 原文:[https://www . geesforgeks . org/Java-program-to-print-the-ascii-value/](https://www.geeksforgeeks.org/java-program-to-print-the-ascii-value/)

ASCII 是美国信息交换标准代码的缩写。在 ASCII 中，给不同的字符和符号指定一个特定的数值，供计算机存储和操作，在存储和操作时，电子设备总是使用给定的 ASCII 数字的二进制值。因为用原始形式是不可能做到的。

**方法:**有 4 种方法可以打印特定字符的 ASCII 值或代码，下面列出了这些方法，简要介绍了实现部分的 java 示例遵循的概念。

1.  **使用蛮力法**
2.  **使用型铸造方法**
3.  **使用格式说明符方法**
4.  **使用字节类方法**

**方法 1:给 int 变量赋值**

为了找到一个字符的 ASCII 值，只需将该字符分配给一个整数类型的新变量。Java 自动将该字符的 ASCII 值存储在新变量中。

**实现**:蛮力法

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print ASCII Value of Character
// by assigning variable to integer

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Character whose ASCII is to be computed
        char ch = '}';

        // Creating a new variable of type int
        // and assigning the character value.
        int ascii = ch;

        /* Java stores the ascii value there itself*/

        // Printing the ASCII value of above character
        System.out.println("The ASCII value of " + ch
                           + " is: " + ascii);
    }
}
```

**Output**

```
The ASCII value of } is: 125
```

**方法二:采用型铸造**

java 中的类型转换是一种将变量转换成另一种数据类型的方法，这意味着保存另一种数据类型的值占用较少的字节。在这种方法中，在打印时，字符是 char 类型到 int 类型的类型转换，它将打印字符的 ASCII 值。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print ASCII Value of Character
// using type-casting

// Importing java generic libraries
import java.util.*;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Character whose ASCII is to be computed
        char ch = '}';

        // Typecasting the character to int and
        // printing the same
        System.out.println("The ASCII value of " + ch
                           + " is: " + (int)ch);
    }
}
```

**Output**

```
The ASCII value of } is: 125
```

> **注:**在上述方法 1 和方法 2 中，两种方法都是一种类型的类型转换。在方法 1 中，类型转换由编译器自动完成。在方法 2 中，手动进行类型转换，因此方法 2 比方法 1 更有效，因为编译器需要付出更少的努力。此外，请记住，自动完成的类型转换称为隐式类型转换，从用户端完成的类型转换称为显式类型转换

**方法 3:使用格式说明符** *(更优)*

在这种方法中，我们借助于 [*格式说明符*](https://www.geeksforgeeks.org/format-specifiers-in-java/) 来生成给定字符的 ASCII 值。我们通过将字符指定为 int，将给定字符的值存储在形式说明符中。因此，该字符的 ASCII 值存储在格式说明符中。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print ASCII Value of Character
// using format specifier

// Importing format library
import java.util.Formatter;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Character whose ASCII is to compute
        char character = '}';

        // Initializing the format specifier
        Formatter formatSpecifier = new Formatter();

        // Converting the character to integer and
        // ASCII value is stored in the format specifier
        formatSpecifier.format("%d", (int)character);

        // Print the corresponding ASCII value
        System.out.println(
            "The ASCII value of the character ' "
            + character + " ' is " + formatSpecifier);
    }
}
```

**Output**

```
The ASCII value of the character ' } ' is 125
```

**方法 4:通过生成字节** *(最佳)*找到 ASCII 值

1.  将字符初始化为字符串。
2.  使用 [getBytes()](https://www.geeksforgeeks.org/java-lang-string-getbyte-java/) 方法创建字节类型的数组。
3.  打印字节数组第“0”个索引处的元素。

这是位于字符串“0”索引处的字符的 ASCII 值。此方法通常用于将整个字符串转换为其 ASCII 值。对于违反编码异常的字符，给出了 try-catch。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print ASCII Value of Character
// by generating bytes. 

// Importing I/O library
import java.io.UnsupportedEncodingException;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Try block to check exception
        try {

            // Character is initiated as a string
            String sp = "}";

            // An array of byte type is ccreated
            // by using getBytes method
            byte[] bytes = sp.getBytes("US-ASCII");

            /*This is the ASCII value of the character
            / present at the '0'th index of above string.*/

            // Printing the element at '0'th index
            // of array(bytes) using charAt() method
            System.out.println("The ASCII value of "
                               + sp.charAt(0) + " is "
                               + bytes[0]);
        }

        // Catch block to handle exception
        catch (UnsupportedEncodingException e) {

            // Message printed foe exception
            System.out.println("OOPs!!!UnsupportedEncodingException occurs.");
        }
    }
}
```

**Output**

```
The ASCII value of } is 125
```