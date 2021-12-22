# Java 程序打印字符串中的新行

> 原文:[https://www . geesforgeks . org/Java-program-to-print-a-new-line-in-string/](https://www.geeksforgeeks.org/java-program-to-print-a-new-line-in-string/)

Java 是最强大的编程语言，通过它我们可以执行许多任务，Java 是一种行业首选语言。所以它充满了大量的特征。在这里，我们将讨论 Java 的一个最好的特性，那就是如何使用 Java 在字符串中打印一个新行。

**方法:**

有许多方法可以打印字符串中的新行，如下所示:

1.  使用 System.lineSeparator()方法
2.  使用平台相关换行符
3.  使用 System.getProperty()方法
4.  使用%n 个换行符
5.  使用 System.out.println()方法

让我们单独详细讨论一下。

**方法 1:** 使用 System.lineSeparator()方法

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print a new line in string
// Using System.lineSeparator() method

// Main class
class GFG {
    // Main Driver Code
    public static void main(String[] args)
    {
        // Calling the System.lineSeparator() function to
        // print newline in between some specified strings
        String newline = System.lineSeparator();

        // Printing new line
        System.out.println("GFG" + newline + "gfg");
    }
}
```

**Output**

```
GFG
gfg

```

**方法 2:** 使用平台相关换行符。

> **注意:**这里新的行字符是 Unix 的“\n”，Windows OS 的“\r\n”。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print a new line in string
// Using platform-dependent Newline Character

// Main class
class GFG {

    // Main Driver Code
    public static void main(String[] args)
    {
        // Using new line Character '\n' to print
        // new line in between strings
        System.out.println("GFG" + '\n' + "gfg");
    }
}
```

**Output**

```
GFG
gfg

```

**方法 3:** 使用 System.getProperty()方法。在这里，该函数使用系统属性“line.separator”的值，该值返回依赖于系统的行分隔符字符串。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print a new line in string

class GFG
{
    // Main Driver Code
    public static void main(String[] args)
    {

        // Calling System.getProperty() function Over The 
        // parameter for the value of the system property "line.separator",
        // which returns the system-dependent line separator string. 
        String newline = System.getProperty("line.separator");

        // Printing new line between two strings
        System.out.println("GFG" + newline + "gfg");
    }
}
```

**输出:**

```
GFG
gfg
```

**方法 4:** 使用%n 个换行符

> **注意:**这里这个换行符和 printf()函数一起使用。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print a new line in string
// Using %n Newline Character

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Main Driver Code
    public static void main(String[] args)
    {
        // Printing new line using new line
        // Character "%n" with the printf() method
        System.out.printf("GFG%ngfg");
    }
}
```

**Output**

```
GFG
gfg
```

**方法-5:** 使用 System.out.println()方法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print a new line in string
// Using System.out.println() method

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Printing new line using
        // System.out.println() function
        // over custom string inputs
        System.out.println("GFG");
        System.out.println("gfg");
    }
}
```

**Output**

```
GFG
gfg

```