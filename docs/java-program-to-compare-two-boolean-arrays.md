# 比较两个布尔数组的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序对两个布尔数组进行比较/](https://www.geeksforgeeks.org/java-program-to-compare-two-boolean-arrays/)

如果两个数组包含相同顺序的相同元素，则它们是相等的。在 java 中，我们可以用两种方式比较两个布尔数组:

*   通过使用 Java 内置方法即 ***。等于()*** 法。
*   通过使用天真的方法。

**示例:**

```java
Input : A = [true , true , false]
        A1 = [true, true, false]

Output: Both the arrays are equal.

Input : A = [true, true, false]
           A1 = [true, false, true]

Output:  Both the arrays are not equal.
```

**方法 1:**

Java 中的数组类提供了方法 **Arrays.equals()** 来检查两个数组是否相等。

**语法:**

```java
public static boolean equals(boolean[] a, boolean[] a1)
```

**参数:**

```java
a - one array to be tested for equality
a1 - another array to be tested for equality
```

**返回:**如果两个数组相等则返回真，否则返回假。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Compare two Boolean
// Arrays using built-in function

import java.util.Arrays;

class GFG {
    public static void main(String[] args)
    {

        // initializing both the boolean arrays
        boolean[] a = new boolean[] { true, true, false };
        boolean[] a1 = new boolean[] { true, true, false };

        // Displaying Array1
        System.out.println("Array1...");

        for (int i = 0; i < a.length; i++) 
        {
            System.out.println(a[i]);
        }

        // Displaying Array2
        System.out.println("Array2...");
        for (int j = 0; j < a1.length; j++) 
        {
            System.out.println(a1[j]);
        }

        // comparing array1 and array2
        boolean result = Arrays.equals(a, a1);

        if (result) 
        {
            System.out.println("Both the arrays equal ");
        }
        else
        {
            System.out.println(
                "Both the arrays not equal ");
        }
    }
}
```

**Output**

```java
Array1...
true
true
false
Array2...
true
true
false
Both the arrays equal
```

**方法二:**

*   在本文中，我们将使用**天真方法**来比较两个数组。
*   我们可以运行 for 循环，检查数组的每个元素，并比较它们。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Compare two Boolean
// Arrays using Naive approach

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // initializing both the boolean arrays
        boolean[] a = new boolean[] { true, true, false };
        boolean[] a1 = new boolean[] { true, true, false };

        // Displaying Array1
        System.out.println("Array1...");
        for (int i = 0; i < a.length; i++) 
        {
            System.out.println(a[i]);
        }

        // Displaying Array2
        System.out.println("Array2...");
        for (int j = 0; j < a1.length; j++) 
        {
            System.out.println(a1[j]);
        }

        // Comparing both the arrays
        for (int i = 0; i < a.length; i++)
        {
            // if any element is found different we will
            // print our ans and exit the program.
            if (a[i] != a1[i]) 
            {
                System.out.println(
                    "Both the arrays equal ");
                System.exit(0);
            }
        }

        System.out.println("Both the arrays equal ");
    }
}
```

**Output**

```java
Array1...
true
true
false
Array2...
true
true
false
Both the arrays equal
```