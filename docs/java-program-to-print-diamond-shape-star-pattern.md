# Java 程序打印菱形星形图案

> 原文:[https://www . geesforgeks . org/Java-程序转打印-菱形-星形-图案/](https://www.geeksforgeeks.org/java-program-to-print-diamond-shape-star-pattern/)

在本文中，我们将学习如何在 Java 中打印菱形星形图案。

插图:

```
Input: number = 7

Output:

       *
      ***
     *****
    *******
   *********
  ***********
 *************
  ***********
   *********
    *******
     *****
      ***
       *
```

**方法:**当涉及到图案印刷时，我们确实选择了仅通过循环印刷的标准方式。我们将尝试不同类型的循环来打印相同的图案。

**示例 1:** 使用边做边循环

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Print Diamond Star Pattern
// Using do-while loop

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring and initializing variables

        // Variable initialized to the row where max star
        // should be there as after that they decreases to
        // give diamond pattern
        int number = 7;

        // Diamond starting with single star in first row,so
        // initialized
        int m = 1;

        // Columnar printing
        int n;

        // Outer loop 1
        // Prints the first half diamond
        do {
            n = 1;

            // Inner loop 1
            // Prints space until ++n <= number - m + 1 is
            // false
            do {
                // Print whitespace between
                System.out.print(" ");

            }

            // Condition for inside do-while loop 1
            while (++n <= number - m + 1);

            // Now
            n = 1;

            // Inner loop 2
            // Prints star until ++n <= m * 2 - 1 is false

            do {

                // Print star
                System.out.print("*");
            }

            // Condition for inner do-while loop 2
            while (++n <= m * 2 - 1);

            // A new row requires a new line
            System.out.println();

        }

        // Condition for outer do-while loop 1
        while (++m <= number);

        // Now we are done with printing the upper half
        // diamond.

        // Note: Not to print the bottom row again in lower
        // half diamond printing Hence variable t be
        // initialized should one lesser than number
        m = number - 1;

        // Outer loop 2
        // Prints the second half diamond
        do {
            n = 1;

            // Inner loop 1
            // Prints space until ++n <= number - m + 1 is
            // false
            do {
                // Print whitespace between
                System.out.print(" ");

            } while (++n <= number - m + 1);

            n = 1;

            // Inner loop 2
            // Prints star until ++n <= m * 2 - 1 is false
            do {
                // Prints star
                System.out.print("*");

            } while (++n <= m * 2 - 1);

            // By now done with one row of lower diamond
            // printing so a new line is required
            System.out.println();

        }

        // Condition for outer do-while loop 2
        while (--m > 0);
    }
}
```

**Output**

```
       *
      ***
     *****
    *******
   *********
  ***********
 *************
  ***********
   *********
    *******
     *****
      ***
       *
```

**示例 2:** 使用 while 循环

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print diamond star pattern
// Using while loop

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declaring and initializing variables

        // Variable initialized to the row where max star
        // should be there as after that they decreases to
        // give diamond pattern
        int number = 7;

        // Diamond starting with single star in first row
        int m = 1;

        // Columnar printing
        int n;

        // Outer loop 1
        // Prints the first half diamond

        // Condition holding true till
        // number of rows initialized
        while (m <= number) {
            n = 1;

            // Inner loop 1
            // Prints space until n++ <= number - m is false
            while (n++ <= number - m) {

                // Print whitespaces inbetween
                System.out.print(" ");
            }

            n = 1;

            // Inner loop 2
            // Prints star until n++ <= m * 2 - 1 is false
            while (n++ <= m * 2 - 1) {

                // Print star
                System.out.print("*");
            }

            // By now we are done for above pyramid printing
            // ending line after each row
            System.out.println();

            // Incrementing as we want pyramid generation
            m++;
        }

        // Now we are done with printing the upper half
        // diamond.

        // Note: Not to print the bottom row again in lower
        // half diamond printing Hence variable t be
        // initialized should one lesser than number
        m = number - 1;

        // Outer loop 2
        // Prints the second half diamond
        while (m > 0) {
            n = 1;

            // Inner loop 1
            // Prints spaces until n++ <= number - m is
            // false
            while (n++ <= number - m) {

                // Print whitespace in between
                System.out.print(" ");
            }

            n = 1;

            // Inner loop 2
            // Prints star until n++ <= m * 2 - 1 is false
            while (n++ <= m * 2 - 1) {

                // Print star
                System.out.print("*");
            }

            // Ending line after each row
            System.out.println();

            // Decrementing as we want reverse pyramid
            // generation
            m--;
        }
    }
}
```

**Output**

```
       *
      ***
     *****
    *******
   *********
  ***********
 *************
  ***********
   *********
    *******
     *****
      ***
       *
```

**示例 3:** 用于循环

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to print diamond star pattern
// Using for loop

// Importing  input output classes
import java.io.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declaring and initializing variables

        // Variable initialized to the row where max star
        // should be there as after that they decreases to
        // give diamond pattern
        int number = 7;

        int m, n;

        // Outer loop 1
        // prints the first half diamond
        for (m = 1; m <= number; m++) {

            // Inner loop 1 print whitespaces inbetween
            for (n = 1; n <= number - m; n++) {
                System.out.print(" ");
            }

            // Inner loop 2 prints star
            for (n = 1; n <= m * 2 - 1; n++) {
                System.out.print("*");
            }

            // Ending line after each row
            System.out.println();
        }

        // Outer loop 2
        // Prints the second half diamond
        for (m = number - 1; m > 0; m--) {

            // Inner loop 1 print whitespaces inbetween
            for (n = 1; n <= number - m; n++) {
                System.out.print(" ");
            }

            // Inner loop 2 print star
            for (n = 1; n <= m * 2 - 1; n++) {
                System.out.print("*");
            }

            // Ending line after each row
            System.out.println();
        }
    }
}
```

**Output**

```
      *
     ***
    *****
   *******
  *********
 ***********
*************
 ***********
  *********
   *******
    *****
     ***
      *
```