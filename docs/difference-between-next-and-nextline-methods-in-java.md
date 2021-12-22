# Java 中 next()和 nextLine()方法的区别

> 原文:[https://www . geesforgeks . org/next-and-next line-methods in-Java/](https://www.geeksforgeeks.org/difference-between-next-and-nextline-methods-in-java/)

[java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中的 [Scanner 类](https://www.geeksforgeeks.org/scanner-class-in-java/)用于获取 int、double 等[原语类型](https://www.geeksforgeeks.org/data-types-in-java/)的输入。和琴弦。这是在 Java 程序中读取输入的最简单的方法，尽管如果您想要一种用于时间受限场景的输入法，比如在[竞争性编程](https://www.geeksforgeeks.org/fast-io-in-java-in-competitive-programming/)中，效率不是很高。扫描仪类由 **next()** 和 **nextLine()** 方法组成。

本文讨论了这两种方法的区别。

**next()方法:**Java 中的 *next()* 方法存在于 [Scanner 类](https://www.geeksforgeeks.org/scanner-class-in-java/)中，用于获取用户的输入。为了使用这种方法，需要创建一个扫描仪[对象](https://www.geeksforgeeks.org/classes-objects-java/)。此方法只能读取输入，直到遇到空格(" ")。换句话说，它从扫描器中找到并返回下一个完整的令牌。

下面是如何在 Java 中实现 next()方法的示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the next() method

import java.util.Scanner;

class GFG {
    public static void main(String[] args)
    {
        // Creating the Scanner object
        Scanner sc = new Scanner(System.in);

        // Use of the next() method
        String Inpt = sc.next();
        System.out.println(Inpt);
    }
}
```

**输入:**

```
Geeks for  
geeks

```

**输出:**

```
Geeks

```

**[nextLine()方法](https://www.geeksforgeeks.org/scanner-nextline-method-in-java-with-examples/):**Java 中的 *nextLine()* 方法存在于 [Scanner 类](https://www.geeksforgeeks.org/scanner-class-in-java/)中，用于获取用户的输入。为了使用这种方法，需要创建一个扫描仪[对象](https://www.geeksforgeeks.org/classes-objects-java/)。这个方法可以读取输入直到行尾。换句话说，它可以接受输入，直到线路改变或新线路，并结束输入获得' \n '或按回车键。

以下是如何在 Java 中实现 nextLine()方法的示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the nextLine() method

import java.util.Scanner;

class GFG {
    public static void main(String[] args)
    {
        // Creating the object of the
        // Scanner class
        Scanner sc = new Scanner(System.in);

        // Use of nextLine() method
        String Inpt = sc.nextLine();
        System.out.println(Inpt);
    }
}
```

**输入:**

```
Geeks for  
geeks

```

**输出:**

```
Geeks for 

```

下表描述了 next()和 nextLine()方法之间的区别:

| **Next()** | **NextLine()** |
| --- | --- |
| 它从输入设备读取输入，直到空格字符。 | 它从输入设备读取输入，直到线路改变。 |
| 它不能读那些有空格的单词。 | 它能读出那些有空格的单词。 |
| 它在获得空间后结束读取输入。 | 它在获得“\n”或按回车键后结束读取输入。 |
| 它在读取输入后将光标放在同一行。 | 它在读取输入后将光标放在下一行。 |
| next()的转义序列是空格。 | 下一行()的转义序列是' \n '。 |
| 扫描输入的语法:
Scanner.next() | 扫描输入的语法:
Scanner.nextLine() |