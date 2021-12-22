# Java 程序打印金字塔数字图案

> 原文:[https://www . geesforgeks . org/Java-程序转打印-金字塔-数字-图案/](https://www.geeksforgeeks.org/java-program-to-print-pyramid-number-pattern/)

在这里，我们在打印模式方面领先了一步，因为在一般情况下，我们通常在特定的行中使用柱状打印，保持在一行中的元素要么全部相加，要么减少，但是随着我们的前进，我们确实开始使用程序中保持外环的行。

**插图:**

```java
A pyramid number pattern of row size r = 5 would look like:
        1 
      2 3 2 
    3 4 5 4 3 
  4 5 6 7 6 5 4 
5 6 7 8 9 8 7 6 5
```

```java
A pyramid number pattern of row size r = 4 would look like:
      1 
    2 3 2 
  3 4 5 4 3 
4 5 6 7 6 5 4 
```

**进场:**

1.  For 循环将用于打印金字塔中的每一行。
2.  在 for 循环中，我们将使用两个循环:
3.  一个循环用于打印空格
4.  第二个循环将用于打印数字。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Print the Pyramid pattern

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        int num = 5;
        int x = 0;

        // Outer loop for rows
        for (int i = 1; i <= num; i++) {
            x = i - 1;

            // inner loop for "i"th row printing
            for (int j = i; j <= num - 1; j++) {

                // First Number Space
                System.out.print(" ");

                // Space between Numbers
                System.out.print("  ");
            }

            // Pyramid printing
            for (int j = 0; j <= x; j++)
                System.out.print((i + j) < 10
                                     ? (i + j) + "  "
                                     : (i + j) + " ");

            for (int j = 1; j <= x; j++)
                System.out.print((i + x - j) < 10
                                     ? (i + x - j) + "  "
                                     : (i + x - j) + " ");

            // By now we reach end for one row, so
            // new line to switch to next
            System.out.println();
        }
    }
}
```

**Output**

```java
            1  
         2  3  2  
      3  4  5  4  3  
   4  5  6  7  6  5  4  
5  6  7  8  9  8  7  6  5  
```