# Java 程序打印金字塔星形图案

> 原文:[https://www . geesforgeks . org/Java-程序转打印-金字塔-星形模式/](https://www.geeksforgeeks.org/java-program-to-print-pyramid-star-pattern/)

本文将指导您完成用 Java 打印金字塔星形图案的过程。

**1。简单的金字塔图案**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

// Java code to demonstrate Pyramid star patterns
public class GeeksForGeeks {
    // Function to demonstrate printing pattern
    public static void PyramidStar(int n)
    {
        int a, b;

        // outer loop to handle number of rows
        // k in this case
        for (a = 0; a < n; a++) {

            // inner loop to handle number of columns
            // values changing acc. to outer loop
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
        PyramidStar(k);
    }
}
```

**Output**

```
* 
* * 
* * * 
* * * * 
* * * * * 
```

**2。旋转 180 度后/镜像模式**

这里我们将打印一个旋转 180 度的星形金字塔。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

// 180 flipped pyramid star pattern
public class GFG {
    // Function to demonstrate printing pattern
    public static void FlippedPyramidStar(int k)
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
        FlippedPyramidStar(k);
    }
}
```

**Output**

```
           * 
         * * 
       * * * 
     * * * * 
   * * * * * 
```

**3。打印三角形:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

// Java code to demonstrate star pattern
public class GeeksForGeeks {
    // Function to demonstrate printing pattern
    public static void printTriagle(int n)
    {
        // outer loop to handle number of rows
        // n in this case
        for (int i = 0; i < n; i++) {

            // inner loop to handle number spaces
            // values changing acc. to requirement
            for (int j = n - i; j > 1; j--) {
                // printing spaces
                System.out.print(" ");
            }

            // inner loop to handle number of columns
            // values changing acc. to outer loop
            for (int j = 0; j <= i; j++) {
                // printing stars
                System.out.print("* ");
            }

            // ending line after each row
            System.out.println();
        }
    }

    // Driver Function
    public static void main(String args[])
    {
        int n = 5;
        printTriagle(n);
    }
}
```

**Output**

```
    * 
   * * 
  * * * 
 * * * * 
* * * * * 
```