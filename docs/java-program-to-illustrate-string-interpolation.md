# 说明字符串插值的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到说明-字符串-插值/](https://www.geeksforgeeks.org/java-program-to-illustrate-string-interpolation/)

字符串内插是一个过程，其中占位符字符被变量(在这种情况下是字符串)替换，这些变量允许动态或有效地打印出文本输出。字符串插值使代码更加紧凑，避免了重复使用变量来打印输出。字符串插值将占位符替换为上述分配给字符串的变量名，因此可以高效地编写大型变量名或文本。

Java 中的字符串插值可以通过几种方式完成，使用一些串联运算符或内置函数或类。

**方法:**

Java 中执行字符串插值的一些方法如下:

1.  使用“+”运算符
2.  使用 format()函数
3.  使用消息格式类
4.  使用字符串生成器类

让我们个别地深入讨论它们

**方法 1:** 使用“+”运算符

我们可以在表达式中双引号之外使用+运算符来处理字符串。变量或字符串名称应根据条件或场景在+运算符之前或之后使用。变量将被它的值替换，因此我们实现了字符串的插值或连接。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate String Interpolation
// Using the + Operator

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Input string

        // String 1
        String name = "Geeks for Geeks";

        // String 2
        String field = "coding";

        // Print and display the string Interpolated
        System.out.println(
            name + " is the best platform to learn "
            + field);
    }
}
```

**Output**

```
Geeks for Geeks is the best platform to learn coding
```

输出解释:

在下面的代码示例中，字符串变量名称和字段通过插入变量名称，在要打印的实际文本之间使用+运算符进行插值或连接。这是连接字符串最简单方便的方法之一，因为它可以根据需求进行定制。运算符也可以不用引号中的文本。

**方法 2:** 使用 format()函数

这种方法将文本与表达式和变量名分开，使其稍微紧凑，便于用于小句子或表达式。占位符(%s 代表字符串)按顺序使用，以适应表达式末尾提供的变量值，因为 format()函数接受字符串作为第一个参数，后跟变量。因此，参数的数量将比字符串中的占位符多一个。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program o Illustrate String Interpolation
// Using the format() method

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom input strings

        // String 1
        String name = "Geeks for Geeks";

        // String 2
        String field = "Data Structures";

        // Print and ddispalt the interpolated string
        System.out.println(String.format(
            "%s is the best platform to learn %s .", name,
            field));
    }
}
```

**Output**

```
Geeks for Geeks is the best platform to learn Data Structures .
```

输出解释:

在上面的代码示例中，我们使用函数 format()通过使用%s 运算符来排列字符串，该运算符用作字符串的占位符。必须在打印字符串的末尾添加顺序字符串，以替换占位符。

**方法 3:** 使用消息格式类

在这个方法中，我们必须导入 MessgeFormat 类，该类为我们提供了格式化函数。MessageFormat 类中的 Format 函数与 String 类中的 format 函数几乎相同，只是占位符的编写方式不同。此函数中的占位符是使用{0}、{1}、{2}等索引编写的..等等。这比字符串类中的 format 函数有一些优势，因为它可以避免重复使用同一个变量。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate String Interpolation
// Using MessageFormat class

// Importing input output class
import java.io.*;
// Importing MessageFormat class from java.text package
import java.text.MessageFormat;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom input strings

        // String 1
        String a = "Democracy";

        // String 2
        String b = "people";

        // Print and display the interpolated string
        System.out.println(MessageFormat.format(
            "{0} is a government of the {1}, for the {1} and by the {1}.",
            a, b));
    }
}
```

**Output**

```
Democracy is a government of the people, for the people and by the people.
```

输出解释:

在上面的代码示例中，很明显，与 String 类函数相比，MessageFormat 类中的 format 函数相当有效。在特定的情况下，我们通过三次写占位符而不是三次或多次写整个变量名来使用变量 b。该功能在大型文本打印或复杂系统中非常有效。

**方法 4:** 使用 StringBuilder 类

由于同样的原因，这种方法相当冗长，也不常用。我们使用 StringBuilder 类实例化一个新对象，并调用 append 函数在 append 函数中的格式化文本之前添加变量。在 StringBuilder 类中，可以链接多达个附加函数。尽管它会使代码的可读性迷失方向。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate String Interpolation
// Using StringBuilder class

// Importing input output libraries
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom inout strings

        // String 1
        String a = "Geeks for Geeks";

        // String 2
        String b = "Data Structure and Algorithms";

        // Print an display the interpolated string
        // using the StringBuilder class and append() method
        System.out.println(
            new StringBuilder(a)
                .append(" is the best portal to learn ")
                .append(b)
                .append("."));
    }
}
```

**Output**

```
Geeks for Geeks is the best portal to learn Data Structure and Algorithms.
```

输出解释:

在上面的代码中，StringBuilder 可选地接受参数作为变量，在这种情况下是字符串，然后我们可以链接 append 函数，用所需的文本插入字符串。

> **结论:**因此，从以上 4 种方法来看，最好的方法将取决于代码的可伸缩性和可读性之间的平衡。可能还有其他方法，一定要探索它们。以上是最常见的方法，因此您只需最少的代码和对语法的理解就可以开始运行。