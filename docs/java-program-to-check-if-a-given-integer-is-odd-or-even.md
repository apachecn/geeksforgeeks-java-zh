# 检查给定整数是奇数还是偶数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查给定整数是奇数还是偶数/](https://www.geeksforgeeks.org/java-program-to-check-if-a-given-integer-is-odd-or-even/)

能被 2 整除并产生 0 的余数的数称为偶数。所有以 0、2、4、6 和 8 结尾的数字都是偶数。另一方面，不能被 2 整除并产生 1 的余数的数称为奇数。所有以 1、3、5、7 和 9 结尾的数字都是奇数。一定要参考下面的插图，通过任何随机整数的普通插图来了解这里应该传达的基本信息，检查它是偶数还是奇数。

```
Input : 13
Output: ODD
```

```
Input : 24
Output: EVEN
```

**方法:**

有各种方法可以检查给定的数字是奇数还是偶数。其中一些方法如下:从强力方法开始，到最优方法结束。

1.  使用暴力-天真的方法
2.  使用按位运算符
    *   使用按位“或”
    *   使用按位“与”
    *   使用按位异或
3.  通过检查最低有效位

**方法 1:** 蛮力天真法

它是检查除以 2 后的余数。能被 2 整除的数是偶数，否则是奇数。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Check if Given Integer is Odd or Even
// Using Brute Forcew Approach

// Importing required classes
import java.io.*;
import java.util.Scanner;

// Main class
class GFG {

    // Main Driver Method
    public static void main(String[] args)
    {
        // Declaring and initializing integer variable
        int num = 10;

        // Checking if number is even or odd number
        // via remainder
        if (num % 2 == 0) {

            // If remainder is zero then this number is even
            System.out.println("Entered Number is Even");
        }

        else {

            // If remainder is not zero then this number is
            // odd
            System.out.println("Entered Number is Odd");
        }
    }
}
```

**Output**

```
Entered Number is Even
```

现在让我们详细讨论优化方法，如下所示，并借助按位运算符

**方法 2:** 使用按位运算符

*   按位“或”
*   按位与或按位异或

**2-A:使用按位或**

偶数按 1 的按位“或”运算使该数的值增加 1，否则该值保持不变。

**图示:**按位“或”

```
    Number = 12              1  1  0  0    - Representation of 12 in Binary Format
                Bitwise OR   0  0  0  1    - Representation of  1 in Binary Format

                             1  1  0  1    - Representation of 13 in Binary Format
    Result- Number was even so bitwise Or by 1 increment the value by 1
```

```
    Number = 15            1  1  1  1    - Representation of 15 in Binary Format
               Bitwise OR  0  0  0  1    - Representation of  1 in Binary Format

                           1  1  1  1    - Representation of 15 in Binary Format
    Result- Number was odd so bitwise Or by 1 doesn't increment the value by 1
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Check if Given Integer is Odd or Even
// Using Bitwise OR

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring and initializing integer variable
        // to be checked
        int n = 100;

        // Condition check
        // if n|1 if greater than n then this number is even
        if ((n | 1) > n) {

            // Print statement
            System.out.println("Number is Even");
        }
        else {

            // Print statement
            System.out.println("Number is Odd");
        }
    }
}
```

**Output**

```
Number is Even
```

**2-B:使用位“与”**

奇数与 1 的按位“与”运算将为 1，因为最后一位已经设置，否则将为 0。

**图示:**按位“与”

```
    Number = 5              0  1  0  1    - Representation of  5 in Binary Format
               Bitwise AND  0  0  0  1    - Representation of  1 in Binary Format

                            0  0  0  1    - Representation of  1 in Binary Format
    Result- Number was odd so bitwise And by 1 is 1
```

```
        Number = 8            1  0  0  0    - Representation of  8 in Binary Format
             Bitwise AND  0  0  0  1    - Representation of  1 in Binary Format

                          0  0  0  0    - Representation of  0 in Binary Format
    Result- Number was even so bitwise And by 1 is 0
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Check if Given Integer is Odd or Even
// Using Bitwise AND

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declare and initializing integer variable
        int n = 91;

        // Condition Check
        // Bitwise AND of any odd number by 1 gives 1
        if ((n & 1) == 1) {

            // Print statement
            System.out.println("Number is Odd");
        }
        else {

            // Print statement
            System.out.println("Number is Even");
        }
    }
}
```

**Output**

```
Number is Odd
```

**2-C:使用按位异或**

偶数按 1 的逐位异或运算将数字的值增加 1，否则如果值为奇数，则将数字的值减少 1。这是最理想的方法。

**图示:**按位异或

```
    Number = 5              0  1  0  1    - Representation of  5 in Binary Format
               Bitwise XOR  0  0  0  1    - Representation of  1 in Binary Format

                            0  1  0  0    - Representation of  4 in Binary Format
    Result- Number was odd so bitwise And by 1 decrement the value
```

```
    Number = 8            1  0  0  0    - Representation of  8 in Binary Format
             Bitwise XOR  0  0  0  1    - Representation of  1 in Binary Format

                          1  0  0  1    - Representation of  9 in Binary Format
    Result- Number was even so bitwise And by 1 increment the value
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Check if Given Integer is Odd or Even
// Using Bitwise XOR

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declare and initializing integer variable
        int num = 99;

        // Condition Check
        // if number^1 increments by 1 then its even number,
        // else odd
        if ((num ^ 1) == num + 1) {

            // Print statement
            System.out.println("Number is Even");
        }
        else {

            // Print statement
            System.out.println("Number is Odd");
        }
    }
}
```

**Output**

```
Number is Odd
```

**方法 3:** 检查数字的最低有效位

偶数的最低有效位总是 0，奇数的最低有效位总是 1。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Check if Given Integer is Odd or Even
// by checking the LSB of the Number

// Importing required classes
import java.util.*;

// Main class
// TestEvenOddByCheckingLSB
public class GFG {

    // Method 1
    // To test number is even or odd
    public static String testOddEvenByCheckingLSB(int a)
    {

        if (a != 0) {
            if (Integer.toBinaryString(a).endsWith("0")) {
                return "Even";
            }
            else {
                return "Odd";
            }
        }

        // Here we will land if
        // it does not ends with 0
        else {
            return "Zero";
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Iterationg over using for loop
        for (int i = 0; i <= 10; i++) {

            // Calling the function and printing
            // corresponding number is even or odd
            System.out.println(
                i + " : " + testOddEvenByCheckingLSB(i));
        }
    }
}
```

**Output**

```
0 : Zero
1 : Odd
2 : Even
3 : Odd
4 : Even
5 : Odd
6 : Even
7 : Odd
8 : Even
9 : Odd
10 : Even
```