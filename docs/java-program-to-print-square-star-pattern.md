# Java 程序打印方形星形图案

> 原文:[https://www . geesforgeks . org/Java-程序转打印-正方形-星形模式/](https://www.geeksforgeeks.org/java-program-to-print-square-star-pattern/)

在这里，我们将实现一个 Java 程序来打印方形星形图案。我们将打印带对角线和不带对角线的方形星形图案。

**示例:**

```java
**********************
*                    *
*                    *
*                    *
*                    *
*                    *
*                    *
**********************
```

**进场:**

**第一步:**输入行数和列数。

**步骤 2:** 对于矩形行，从 1 到行运行外部循环。

```java
for (i = 1; i < = rows; i++)
```

**步骤 3:** 对于矩形的列，运行从 1 到列的内部循环。

```java
for (j = 1; j < = columns; j++)
```

**第四步:**第一行或最后一行或第一列或最后一列打印星号，否则打印空格。

**第五步:**打印完一行的所有列后，在内环后打印换行符。

**例 1:** 无对角线的星形正方形图案

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Print Square Pattern
// Case 1: Hollow rectangle

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Method 1
    // To print hollow rectangle
    static void print_rectangle(int k, int l)
    {
        int a, b;

        // Nested for loops for iterations

        // Outer loop for rows
        for (a = 1; a <= k; a++) {
            // Inner loop for columns
            for (b = 1; b <= l; b++) {
                // Condition check using logical OR operator
                // over rows and columns positions
                // if found at circumference of rectangle
                if (a == 1 || a == k || b == 1 || b == l)

                    // Print the star pattern
                    System.out.print("*");
                else

                    // Rest inside square print the empty
                    // spaces
                    System.out.print(" ");
            }

            // By now we are done with only 1 row so
            // New line
            System.out.println();
        }
    }

    // Method 2
    // Main driver method
    public static void main(String args[])
    {
        // Declaring and initializing rows and columns
        // For square row = columns

        // Custom input initialization values
        int rows = 8, columns = 22;

        // Calling the method1 to print hollow rectangle
        // pattern
        print_rectangle(rows, columns);
    }
}
```

**Output**

```java
**********************
*                    *
*                    *
*                    *
*                    *
*                    *
*                    *
**********************
```

现在更进一步，如上所述，我们只需在矩形内插入空格。在数学中，我们已经遇到了对角线，所以我们也可以在上面的情况下打印它们。

**例 2:** 带对角线的星形方形图案

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Print Square Star pattern
// Case: Primary and secondary diagonal Rectangle Pattern
import java.io.*;

// Mai class
class GFG {

    // Method 1
    // To print square with primary and secondary diagonal
    static void print_squaredi(int k)
    {
        int a, b;

        // Nested 2 for loops for Matrix rinting

        // Outer loop for rows
        for (a = 1; a <= k; a++) {
            // Inner loop for columns
            for (b = 1; b <= k; b++) {
                // Condition check using OR operator where
                // 1\. Printing star as per first 4 checks
                // on the circumference of rectangle
                // 2\. Fifth check is for diagonals
                if (a == 1 || a == k || b == 1 || b == k
                    || a == b || b == (k - a + 1))

                    // Print the star pattern
                    System.out.print("*");
                else

                    // Print the white spaces
                    System.out.print(" ");
            }

            // By now we are over with one row so
            // new line
            System.out.println();
        }
    }

    // Method 2
    // Main driver method
    public static void main(String args[])
    {
        // This time taking square so only one variable
        // needs to be declared
        // Custom input entry
        int rows = 12;

        // calling the method1 to print
        // square pattern with diagonal
        print_squaredi(rows);
    }
}
```

**Output**

```java
************
**        **
* *      * *
*  *    *  *
*   *  *   *
*    **    *
*    **    *
*   *  *   *
*  *    *  *
* *      * *
**        **
************
```