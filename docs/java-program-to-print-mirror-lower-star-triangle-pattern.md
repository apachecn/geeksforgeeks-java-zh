# Java 程序打印镜像下星形三角图案

> 原文:[https://www . geesforgeks . org/Java-程序转打印-镜像-下-星-三角-图案/](https://www.geeksforgeeks.org/java-program-to-print-mirror-lower-star-triangle-pattern/)

在本文中，我们将学习如何在 Java 中打印镜像下星形三角形图案。

插图:

```
Input: number = 7
Output:
* * * * * * * 
 * * * * * * 
  * * * * * 
   * * * * 
    * * * 
     * * 
      * 
      * 
     * * 
    * * * 
   * * * * 
  * * * * * 
 * * * * * * 
* * * * * * * 
```

方法:我们可以使用循环打印镜像下星形三角图案，所以

1.  用于循环
2.  使用 while 循环
3.  使用边做边循环

**方法 1:** 用于循环

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print Mirror Lower Star Triangle Pattern
// Using For loop
import java.io.*;

// Main class
class GFG {

    // Method
    // Main driver method
    public static void main(String[] args)
    {
        // Declare and initialize variable to
        // Size of the triangle
        int number = 7;

        // Declaring two variables for rows and columns
        int m, n;

        // Outer loop 1
        // Prints the first half triangle
        for (m = 1; m <= number; m++) {

            // Inner loop 1
            for (n = 1; n < m; n++) {
                // Print whitespace
                System.out.print(" ");
            }

            // Inner loop 2
            for (n = m; n <= number; n++) {
                // Print star
                System.out.print("*"
                                 + " ");
            }

            // Ending line after each row
            System.out.println();
        }

        // Outer loop 2
        // prints the second half triangle
        for (m = number - 1; m >= 0; m--) {

            // Inner loop 1
            for (n = 0; n < m; n++) {
                // Print whitespace
                System.out.print(" ");
            }

            // Inner loop 2
            for (n = m; n <= number - 1; n++) {
                // Print star
                System.out.print("*"
                                 + " ");
            }

            // Ending line after each row
            System.out.println();
        }
    }
}
```

**Output**

```
* * * * * * * 
 * * * * * * 
  * * * * * 
   * * * * 
    * * * 
     * * 
      * 
      * 
     * * 
    * * * 
   * * * * 
  * * * * * 
 * * * * * * 
* * * * * * * 

```

**方法 2:** 使用 While 循环

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Print Mirror Lower Star Triangle Pattern
// using While loop
import java.io.*;

// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declare and initialize variable to
        // Size of the triangle
        int number = 7;

        int m = number;
        int n;

        // Outer loop 1
        // prints the first half triangle

        // ill condition holds true
        while (m > 0) {
            n = 0;

            // Inner loop 1
            // prints space until n++ < number - m is false
            while (n++ < number - m) {
                // print whitespace
                System.out.print(" ");
            }

            n = 0;

            // Inner loop 2
            // Prints star until n++ < (m * 2) - 1 is false
            while (n++ < (m * 2) - 1) {
                // Print star
                System.out.print("*");
            }

            // Ending line after each row
            System.out.println();

            // Decrementing by one
            m--;
        }

        m = 1;

        // Outer loop 2
        // prints the second half triangle
        while (m <= number) {
            n = 0;

            // Inner loop 1
            // prints space until n++ < number - m is false
            while (n++ < number - m) {
                // Print whitespace
                System.out.print(" ");
            }

            n = 0;

            // Inner loop 2
            // Prints star until n++ < (m * 2) - 1 is false
            while (n++ < (m * 2) - 1) {
                // print star
                System.out.print("*");
            }

            // Ending line after each row
            System.out.println();

            m++;
        }
    }
}
```

**Output**

```
*************
 ***********
  *********
   *******
    *****
     ***
      *
      *
     ***
    *****
   *******
  *********
 ***********
*************

```

**输出:**

**方法 3:** 使用边做边循环

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print Mirror Lower Star Triangle Pattern
// using Do-while loop
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declare variable with the
        // Size of the triangle
        int number = 7;

        int m = number;
        int n;

        // Outer loop 1
        // prints the first half triangle
        do {
            n = 0;

            // Inner loop 1
            // prints space until n++ < number - m is false
            do {
                // Print whitespaces
                System.out.print(" ");

            } while (n++ < number - m);

            n = 0;

            // Inner loop 2
            // prints star until n++ < m * 2 - 2 is false
            do {
                // Print star
                System.out.print("*");
            }

            while (n++ < m * 2 - 2);

            System.out.println("");

        }

        // Condition check for do-while
        while (--m > 0);

        m = 1;

        // Outer loop 2
        // prints the second half triangle
        do {
            n = 0;

            // Inner loop 1
            // prints space until n++ < (number - m) is
            // false
            do {
                // Print whitespace
                System.out.print(" ");

            } while (n++ < (number - m));

            n = 0;

            // Inner loop 2
            // prints star until n++ < (m * 2) - 2 is false
            do {
                // Print star
                System.out.print("*");
            }

            while (n++ < (m * 2) - 2);

            System.out.println("");

        }

        // Condition check for do-while
        while (++m <= number);
    }
}
```

**Output**

```
 *************
  ***********
   *********
    *******
     *****
      ***
       *
       *
      ***
     *****
    *******
   *********
  ***********
 *************

```