# Java 字符串类缩进()方法示例

> 原文:[https://www . geesforgeks . org/Java-string-class-indent-method-with-examples/](https://www.geeksforgeeks.org/java-string-class-indent-method-with-examples/)

JDK 12 在 Java.lang.String 类中引入了*缩进()*方法。此方法用于在行的**开头添加或删除空格，以调整每个字符串行的缩进。**

****语法:****

```java
public String indent(int n)
```

****参数:**以整数 n 为输入，做相应缩进。**

> **此外，每行都以“\n”(一个换行符)为后缀。**

****程序:****

**当字符串被提供给*缩进()*方法时，**

1.  **它调用 lines()函数**
2.  **然后，对于每一行，根据下面讨论的用户案例提供的整数值进行缩进:

    *   如果 n>0(正)
        *   然后在每一行的开头加上 n 个空格，每行以“\n”为后缀。
    *   如果 n==0
        *   然后缩进保持不变，只有一行以“\n”为后缀。
    *   如果 n<0(负)，则
        *   如果(+n)>前导空格可用
            *   然后删除每行的所有前导空格，每行以“\n”为后缀
        *   如果(+n)
            *   然后删除每行的(+n)个前导空格，每行以“\n”为后缀** 
3.  **然后，用“\n”给每一行加后缀。**
4.  **然后，连接结果字符串行并返回**

****实施:****

****例 1****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to illustrate indent() method of
// String class

// Importing basic libraries
import java.io.*;
import java.util.*;

// Class for indent() method
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Custom input string
        String input
            = "GeeksforGeeks\nA Computer Science portal for geeks.";

        // Print and display the input string
        System.out.println(input);

        // Print the above string length
        // using standard length() method
        System.out.println("Input String length: "
                           + input.length());

        // Now, calling the indent() method
        // for random value of N

        // Case 1: N>0 | Positive
        // Say N = 5 which is positive
        // so as per procedural algorithm
        // 5 white spaces are added
        // at the starting of each line
        String output = input.indent(5);

        // Print and display output string
        System.out.println(output);

        // Print the new string length
        // again using the length() method
        System.out.println("New String length: "
                           + output.length());

        // Case 2: N=0 | Zero
        // Call indent method with n=0
        String output1 = input.indent(0);
        System.out.println(output1);
        System.out.println("New String length: "
                           + output1.length());

        // Case 3: N < 0 | Negative
        // Call indent method with n=-3 (negative)
        String output2 = input.indent(-3);

        // Print the output string
        System.out.println(output);

        // Print output(new) string length
        System.out.println("New String length: "
                           + output2.length());
    }
}
```

****输出:****

```java
GeeksforGeeks
A Computer Science portal for geeks.
Input String length: 50
    GeeksforGeeks
    A Computer Science portal for geeks.

New String length: 61
GeeksforGeeks
A Computer Science portal for geeks.

New String length: 51
GeeksforGeeks
A Computer Science portal for geeks.

New String length: 51
```

****例 2:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to illustrate indent() method of
// String class

// Importing basic libraries
import java.util.*;
import java.io.*;

// Class for indent() method
public class GFG {

  // Main driver method
    public static void main(String args[])
    {
        // Input string
        String input = "GeeksforGeeks";
        System.out.println(input);
        System.out.println("Input String length: "
                           + input.length());

        // Call indent method on input string with n=5
        // (positive)
        String output = input.indent(5);
        System.out.println(output);
        System.out.println("New String length: "
                           + output.length());

        // Call indent method on output string with n=0
        String output1 = output.indent(0);
        System.out.println(output1);
        System.out.println("New String length: "
                           + output1.length());

        // Call indent method on output1 string with n=-3
        // (negative)
        String output2 = output.indent(-3);
        System.out.println(output2);
        System.out.println("New String length: "
                           + output2.length());
    }
}
```

****输出:****

```java
GeeksforGeeks
Input String length: 13
    GeeksforGeeks

New String length: 19
    GeeksforGeeks

New String length: 19
 GeeksforGeeks

New String length: 16
```