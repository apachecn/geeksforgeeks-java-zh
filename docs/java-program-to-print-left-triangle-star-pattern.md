# Java 程序打印左三角星形图案

> 原文:[https://www . geesforgeks . org/Java-程序到打印-左三角-星形模式/](https://www.geeksforgeeks.org/java-program-to-print-left-triangle-star-pattern/)

在这篇文章中，我们将学习打印左三角星形图案。

**示例:**

```java
Input : n = 5
Output: 
           * 
         * * 
       * * * 
     * * * * 
   * * * * * 
```

**左三角星形图案:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;

// java program for left triangle
public class GFG {
    // Function to demonstrate printing pattern
    public static void StarleftTriangle(int k)
    {
        int a, b;

        // 1st loop
        for (a = 0; a < k; a++) {

            // nested 2nd loop
            for (b = 2 * (k - a); b >= 0; b--) {
                // printing spaces
                System.out.print(" ");
            }

            // nested 3rd loop
            for (b = 0; b <= a; b++) {
                // printing stars
                System.out.print("* ");
            }

            // end-line
            System.out.println();
        }
    }

    // Driver Function
    public static void main(String args[])
    {
        int k = 5;
        StarleftTriangle(k);
    }
}
```

**Output**

```java
           * 
         * * 
       * * * 
     * * * * 
   * * * * * 
```