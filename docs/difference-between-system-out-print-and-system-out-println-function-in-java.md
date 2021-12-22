# Java 中 System.out.print()和 System.out.println()函数的区别

> 原文:[https://www . geesforgeks . org/system-out-print-and-system-out-println-function-in-Java/](https://www.geeksforgeeks.org/difference-between-system-out-print-and-system-out-println-function-in-java/)区别

在 Java 中，我们有以下函数来打印控制台中的任何内容。

*   *System.out.print()* 和
*   *System.out.println()*

但两者略有不同，即

***system . out . println()***打印内容并在语句执行后切换到下一行

***system . out . print()***只打印内容，执行此语句后不切换到下一行。

下面的例子将帮助你更突出地理解它们之间的区别。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        System.out.println("Welcome to JAVA (1st line)"); 

          // this print statement will be printed in a new line.
        System.out.print("Welcome to GeeksforGeeks (2nd line) "); 

          // this print statement will be printed in the same line.
        System.out.print("Hello Geeks (2nd line)");
    }
}
```

**Output**

```java
Welcome to JAVA (1st line)
Welcome to GeeksforGeeks (2nd line) Hello Geeks (2nd line)
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        System.out.print("Welcome to JAVA (1st line) "); 

          // this print statement will be printed in the same line.
        System.out.println("Welcome to GeeksforGeeks (1st line)"); 

          // this print statement will be printed in a new line.
        System.out.print("Hello Geeks (2nd line)");
    }
}
```

**Output**

```java
Welcome to JAVA (1st line) Welcome to GeeksforGeeks (1st line)
Hello Geeks (2nd line)
```