# Java 程序交换两个数字

> 原文:[https://www . geesforgeks . org/Java-程序到交换-两个数字/](https://www.geeksforgeeks.org/java-program-to-swap-two-numbers/)

**问题陈述:**给定两个整数 m 和 n，目标只是在内存块中交换它们的值，并编写演示方法的 java 代码。

插图:

```
Input  : m=9, n=5
Output : m=5, n=9

Input  : m=15, n=5
Output : m=5, n=15
Here 'm' and 'n' are integer value
```

**接近:**

有 3 种标准方法可以交换不同空间和时间复杂度的号码。

1.  在存储器中创建辅助存储单元。
2.  而不产生任何辅助(附加)存储单元
3.  使用异或(按位异或)运算符

![](img/3fcdf31afa78a01719e3cde5e68928cd.png)

下面按照上面列出的相同顺序分别描述这些方法:

**方法 1:使用第三个变量**交换值

将在存储器的堆栈区域中占据相同存储器的相同类型的存储器中创建存储器单元。在执行过程中，它保留一个值来替换其他值，一旦期望的执行完成，它的值被分配给已经存在的第二个变量。一旦变量的范围是三个，就从存储单元中释放变量。这个变量被称为临时变量，或者有时被称为催化剂，因为输出中的参与甚至没有被跟踪，但是执行将停止以产生上述预期的结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Swap Two values using third variable
// using temp variable

// Importing generic libraries
import java.util.*;

class GFG {

    // Function to swap two numbers
    // Using temporary variable
    static void swapValuesUsingThirdVariable(int m, int n)
    {
        // Swapping the values
        int temp = m;
        m = n;
        n = temp;
        System.out.println("Value of m is " + m
                           + " and Value of n is " + n);
    }

    // Main driver code
    public static void main(String[] args)
    {
        // Random integerslues
        int m = 9, n = 5;

        // Calling above function to
        // reverse the numbers
        swapValuesUsingThirdVariable(m, n);
    }
}
```

**Output**

```
Value of m is 5 and Value of n is 9
```

**方法 2:** 利用数学中的和与差概念，在不使用第三变量的情况下交换值。

**算法**:有如下 3 个标准步骤:

1.  第二个数字与第一个数字的差值存储在已经存储了第一个数字的存储单元中。
2.  两个数字的总和存储在第二存储单元(数字)中。
3.  计算第一个数字与第二个数字的差值，并将其存储在存储单元中，在该存储单元中存储了初始的第一个值。

下面是在不在内存中创建任何辅助空间的情况下交换数字的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to swap the two values
// without using third variable

// Importing generic Java libraries
import java.util.*;

class GFG {

    // Function to swap values of two numbers
    // without creating temp variable
    static void swapValuesWithoutUsingThirdVariable(int m,
                                                    int n)
    {
        // Steps as listed in algorithm

        // Difference of 2nd from 1st
        // is stored in first variable
        m = m - n;

        // Sum is stored in second variable
        n = m + n;

        // Difference of 1st from 2nd
        // is replaced in first variable
        m = n - m;

        // Print numbers
        System.out.println("Value of m is " + m
                           + " and Value of n is " + n);
    }

    //  Main driver method
    public static void main(String[] args)
    {
        // Random numbers of integer type
        int m = 9, n = 5;

        // Above function is called in main
        // to print swapped values of numbers
        swapValuesWithoutUsingThirdVariable(m, n);
    }
}
```

**Output**

```
Value of m is 5 and Value of n is 9
```

**方法 3:** 使用运算符交换值

逐位运算符用于对数字的各个位进行操作。它们可以与任何整数类型(char、short、int 等)一起使用。它们在执行二进制索引树的更新和查询操作时使用。

这个算子是二元算子，用'^'.表示它返回输入值的逐位异或，即如果对应的位不同，它给出 1，否则给出 0。

插图:

```
a = 5 = 0101 (In Binary)
b = 7 = 0111 (In Binary)

Bitwise XOR Operation of 5 and 7
  0101
^ 0111
 ________
  0010  = 2 (In decimal)
```

这是最理想的方法，因为这里直接计算是在比特上进行的，而不是上面两种方法中看到的字节。这是一个展示内部工作的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to swap the two values
// using XOR Operator

// Importing generic Java libraries
import java.io.*;

class GFG {

    // Function to swap values of two numbers
    // using XOR operator
    static void swapValuesUsingXOROperator(int m, int n)
    {
        // Logic of XOR operator
        m = m ^ n;
        n = m ^ n;
        m = m ^ n;

        System.out.println("Value of m is " + m
                           + " and Value of n is " + n);
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Random two integer numbers
        // to get swapped
        int m = 9, n = 5;

        // Calling the function in main method
        // to get above integer numbers swapped
        swapValuesUsingXOROperator(m, n);
    }
}
```

**Output**

```
Value of m is 5 and Value of n is 9
```