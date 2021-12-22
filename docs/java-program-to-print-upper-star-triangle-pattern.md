# Java 程序打印上星三角图案

> 原文:[https://www . geesforgeks . org/Java-program-to-print-upper-star-triangle-pattern/](https://www.geeksforgeeks.org/java-program-to-print-upper-star-triangle-pattern/)

上面的星形三角形图案意味着底部必须在底部，并且在第一行只打印一颗星。这里将出现的问题是我们向前或向后遍历的方式，我们不能忽略空格，所以我们不能在第一行中仅使用两个嵌套的 for 循环来打印星形。这个问题的答案很简单，因为我们将这个问题分成两半，我们将运行两个循环的 inners，一个管理空白，另一个管理模式打印 rest 保持不变。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to  Print Upper Star Triangle Pattern

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declaring and initializing variable representing
        // number of rows to be printed
        int k = 9;

        // Nested 2 for loops for iterating over the matrix

        // Outer for loop for iterating over rows
        for (int a = 0; a <= k; a++) {

            // Inner for loop for iterating over columns
            // where we are printing white spaces
            for (int b = 1; b <= k - a; b++) {

                // Print the white space
                System.out.print(" ");
            }

            // Inner for loop for iterating over columns
            // where we are printing white spaces
            for (int l = 0; l <= a; l++) {

                // Print the star pattern
                System.out.print("*");
            }

            // By now we are done with one row so
            // next line
            System.out.println("");
        }
    }
}
```

**Output**

```
         *
        **
       ***
      ****
     *****
    ******
   *******
  ********
 *********
**********
```