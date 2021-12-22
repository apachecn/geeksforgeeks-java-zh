# 递归求一个数的阶乘的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-查找-数字的阶乘-递归/](https://www.geeksforgeeks.org/java-program-to-find-factorial-of-a-number-recursively/)

n 的阶乘定义为所有正的递减整数的乘积，n 的阶乘用 n 表示！。阶乘可以使用以下递归公式计算，其中递归调用的所有数字的多样性小于计算阶乘的数字，因为计算阶乘的公式如下:

```java
n! = n * [(n-1)!] 
i.e factorial of n (n!) = n * (n-1) * ......* 3 * 2* 1
```

**注:**0 的阶乘为 1

**插图:**

```java
Input      : 5!
Processing : 5*4*3*2*1
Output     : 120  
```

```java
Input      : 6!
Processing : 6*5*4*3*2*1
Output     : 720 
```

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Find Factorial of a Number
// where N>=0 is currently N>1

// Importing input output classes
import java.io.*;
// importing utiltity classes
import java.util.*;

// Main class
class GFG {

    // Method 1
    // To calculate factorial
    static int factorial(int n)
    {

        // Handling base case
        // iIf value of n=1 or n=0, it returns 1
        if (n == 0 || n == 1)
            return 1;

        // Generic case
        // Otherwise we do n*(n-1)!
        return n * factorial(n - 1);
    }

    // Method 2
    // main driver method
    public static void main(String[] args)
    {

        // Calling method 1 to compute factorial and
        // storing the result into a variable
        int ans = factorial(5);

        // Print and display the factorial of number
        // customly passed as an argument
        System.out.println("Factorial of 5 is :" + ans);
    }
}
```

**Output**

```java
Factorial of 5 is :120
```

**输出解释:**

最初，阶乘()是从主方法调用的，5 作为参数传递。因为 5 大于或等于 1，所以 5 乘以阶乘( )的结果，其中 4 (n -1)被传递。因为它是从同一个方法调用的，所以它是递归调用。在每次递归调用中，参数 n 的值减少 1，直到 n 小于 1。当 n 的值小于或等于 1 时，则没有递归调用，最后返回 1。

**例 2:**

## Java

```java
// Java Program to Find Factorial of a Number
// where N>=0 is currently N=1

// Importing input output classes
import java.io.*;
// Importing utility classes
import java.util.*;

// Main class
class GFG {

    // Method 1
    // To calculate factorial
    static int factorial(int n)
    {

        // Handling base case
        // If value of n=1 or n=0 we return 1
        if (n == 0 || n == 1)
            return 1;

        // Generic case computation math
        // Otherwise we do n*(n-1)!
        return n * factorial(n - 1);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Calling Method 1 and
        // storing the result into variable
        int ans1 = factorial(0);
        int ans2 = factorial(1);

        // Print and display the factorial of 0
        System.out.println("Factorial of 0 is : " + ans1);

        // Similarly, Print and display the factorial of 1
        System.out.println("Factorial of 1 is : " + ans2);
    }
}
```

**输出**

```java
Factorial of 0 is : 1
Factorial of 1 is : 1
```

**输出解释:**

最初，阶乘( )是从主方法调用的，6 作为参数传递。在每次递归调用中，参数 n 的值减少 1，直到 n 小于 1。为了 1！传递的减少参数是 0！作为一个要计算的小递归调用。如上所述，零的阶乘是 1。因此，返回的小答案是 1，随后再乘以 1，结果 1 作为输出。因此，声明当 n 的值小于或等于 0 时，不计算递归调用，因为我们将遇到不允许计算阶乘的负整数。