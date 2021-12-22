# Java 程序打印向下三角形星形图案

> 原文:[https://www . geesforgeks . org/Java-程序到打印-向下-三角形-星形模式/](https://www.geeksforgeeks.org/java-program-to-print-downward-triangle-star-pattern/)

向下的三角形星形图案表示我们想要打印一个面向下的三角形，这意味着底部是向上的，默认情况下，方向是向左的，所以想要打印的三角形应该看起来像

```java
* * * *
* * *
* *
*
```

**示例**

## Java

```java
// Java Program to Print Lower Star Triangle Pattern

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Nested 2 for loops for iteration over the matrix

        // Outer loop for rows
        int rows = 9;
        for (int a = rows - 1; a >= 0; a--) {

            // Inner loop for columns
            for (int b = 0; b <= a; b++) {

                // Prints star and space
                System.out.print("*"
                                 + " ");
            }

            // By now we are done with single row so new
            // line
            System.out.println();
        }
    }
}
```

**输出**

```java
* * * * * * * * * 
* * * * * * * * 
* * * * * * * 
* * * * * * 
* * * * * 
* * * * 
* * * 
* * 
* 

```