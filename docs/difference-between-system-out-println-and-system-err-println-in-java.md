# Java 中 System.out.println()和 System.err.println()的区别

> 原文:[https://www . geesforgeks . org/system-out-println-and-system-err-println-in-Java/](https://www.geeksforgeeks.org/difference-between-system-out-println-and-system-err-println-in-java/)之间的差异

**System.out** 是一个我们可以写入字符的打印流。它输出我们在命令行界面控制台/终端上写入的数据。它主要用于控制台应用程序/程序向用户显示结果。它在调试小程序时也很有用。

**语法:**

```java
System.out.println("Your Text which you want to display");
```

**例:**

## 爪哇

```java
// Java program to Demonstrate Use of System.out.println()

// Importing required input output classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Print statement
        System.out.println("GeeksForGeeks!");
    }
}
```

**输出**

```java
GeeksForGeeks!
```