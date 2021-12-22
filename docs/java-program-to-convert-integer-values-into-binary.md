# 将整数值转换为二进制的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-将整数值转换为二进制/](https://www.geeksforgeeks.org/java-program-to-convert-integer-values-into-binary/)

整数是基值为 10 的数字。二进制数是以 2 为基数表示的数。二进制仅由 2 个数字 0 和 1 组成。在整数到二进制模的转换和给定输入到二进制数的除法中使用了两个运算符。

**例:**

```java
Input:  = 45
Output: = 101101

Input:  = 32
Output: = 100000
```

将整数转换成二进制数的方法有很多，这里讨论其中的一些。我们将讨论其中的两个:

*   **Implementation of stack**
*   **使用内置方法-**[**t*****obinarinstring()***](https://www.geeksforgeeks.org/java-lang-integer-class-methods/)****Java 的整数类****

****方法 1:使用栈的实现****

**实际上，二进制数只由 0 和 1 组成。要将整数转换为二进制，请将数字除以 2，直到它变成 0。在每一步中取模 2，并将余数存储到数组或堆栈中。如果我们将余数存储到一个数组中，然后以相反的顺序打印出来。如果我们将剩余部分存储到堆栈中，那么只需逐个弹出元素并打印出来。**

**下面是上述方法的 java 实现:**

**T3】JavaT5

```java
// Java Program to Convert Integer Values into Binary

// Importing CLasses/Files
import java.io.*;

public class GFG {
    // Function to print binary number
    static void printBinary(int[] binary, int id)
    {
        // Iteration over array
        for (int i = id - 1; i >= 0; i--)
            System.out.print(binary[i] + "");
    }

    // Function converting decimal to binary
    public static void decimalToBinary(int num)
    {
        // Creating and assigning binary array size
        int[] binary = new int[35];
        int id = 0;

        // Number should be positive
        while (num > 0) {
            binary[id++] = num % 2;
            num = num / 2;
        }

        // Print Binary
        printBinary(binary, id);
    }

    // Main Driver Code
    public static void main(String[] args)
    {
        // Entered number to be convert into binary
        int num = 45;

        // Calling Our Above Function
        decimalToBinary(num);
    }
}
```

T6****T8**输出**T1

**使用堆栈通过创建对象向量**

## Java

```java
// Java Program to Convert Integer Values into Binary

// Importing Classes/Files
import java.io.*;
import java.util.Stack;

public class GFG {

    // Function to convert integer to binary
    static void decimalToBinary(int num)
    {
        // Creating Stack Object Vector
        Stack<Integer> st = new Stack<>();

        // Number Should be positive
        while (num > 0) {

            // Pushing numbers inside stack that
            // are divisible by 2
            st.push(num % 2);
            // Dividing number by 2
            num = num / 2;
        }

        // Checking condition whether stack is empty
        while (!(st.isEmpty())) {

            // Printing binary number
            System.out.print(st.pop());
        }
    }

    // Main driver function
    public static void main(String[] args)
    {
        // Entered number to be converted into binary
        int num = 45;
        decimalToBinary(num);
    }
}
```

**输出**

```java
101101
```

**方法二:使用**[***toBinaryString()***](https://www.geeksforgeeks.org/java-lang-integer-tobinarystring-method/)****Java 的整数类的内置方法****

## **Java**

```java
// Java Program to Convert Integer Values into Binary

// Importing Classes/Files
import java.io.*;

class GFG {
    // Function converting decimal to binary
    static void decimalToBinary(int num)
    {
        // Function to print integer to binary using
        // inbuilt toBinaryString method
        System.out.println(Integer.toBinaryString(num));
    }

    // Main driver function
    public static void main(String[] args)
    {
        // Number to be converted into binary
        int num = 45;

        // Calling function
        decimalToBinary(num);
    }
}
```

****输出**

```java
101101
```

T25】****