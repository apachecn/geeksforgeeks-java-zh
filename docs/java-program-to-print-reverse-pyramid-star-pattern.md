# Java 程序打印倒金字塔星形图案

> 原文:[https://www . geesforgeks . org/Java-程序到打印-反向-金字塔-星形模式/](https://www.geeksforgeeks.org/java-program-to-print-reverse-pyramid-star-pattern/)

**进场:**

1.使用扫描器类或 BufferedReader 类对象从用户处获取输入行数。

2.现在运行两个循环

*   在初始化时循环遍历许多行，或者从 java 中的 reader 类对象获取输入。现在，
    *   从 1 到“i-1”运行一个内环
    *   从 1 到行* 2 –( I×2–1)的另一个内部循环

插图:

```java
Input: number = 7

Output:

*************
 ***********
  *********
   *******
    *****
     ***
      *
```

**方法:**我们可以使用以下方法打印倒金字塔星形图案:

1.  使用 while 循环
2.  用于循环
3.  使用边做边循环

**示例 1:** 使用 While 循环

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Print Reverse Pyramid Star Pattern
// Using While loop

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring and initializing variable to
        // Size of the pyramid
        int number = 7;

        int i = number, j;

        // Nested while loops
        // Outer loop

        // Till condition holds true
        while (i > 0) {
            j = 0;

            // Inner loop
            // Condition check
            while (j++ < number - i) {
                // Print whitespaces
                System.out.print(" ");
            }

            j = 0;

            // Inner loop
            // Condition check
            while (j++ < (i * 2) - 1) {
                // Print star
                System.out.print("*");
            }

            // By now, we reach end of execution for one row
            // so next line
            System.out.println();

            // Decrementing counter because we want to print
            // reverse of pyramid
            i--;
        }
    }
}
```

**Output**

```java
*************
 ***********
  *********
   *******
    *****
     ***
      *
```

**示例 2:** 用于循环

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print reverse pyramid star pattern
// Using for loop
import java.io.*;

class GFG{

public static void main (String[] args) 
{

    // Size of the pyramid
    int number = 7;
    int i, j;

    // Outer loop handle the number of rows
    for(i = number; i >= 1; i--)
    {

        // Inner loop print space
        for(j = i; j < number; j++)
        {
            System.out.print(" ");
        }

        // Inner loop print star
        for(j = 1; j <= (2 * i - 1); j++)
        {
            System.out.print("*");
        }

        // Ending line after each row
        System.out.println("");
    } 
}
}
```

**Output**

```java
*************
 ***********
  *********
   *******
    *****
     ***
      *
```

**示例 3:** 使用边做边循环

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Print Reverse Pyramid Star Pattern
// Using do-while loop

// Importing input output classes
import java.io.*;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declare and initialize variable to
        // Size of the pyramid
        int number = 7;

        int i = number, j;

        // Outer loop iterate until i > 0 is false
        do {
            j = 0;

            // First inner do-while loop
            do {

                // Prints space until j++ < number - i is
                // false
                System.out.print(" ");
            } while (j++ < number - i);
            j = 0;

            // Second inner do-while loop

            // Inner loop prints star
            // until j++ < i * 2 - 2 is false
            do {

                // print star
                System.out.print("*");
            }

            while (j++ < i * 2 - 2);

            // Print whitespace
            System.out.println("");
        }

        // while of outer 'do-while' loop
        while (--i > 0);
    }
}
```

**Output**

```java
 *************
  ***********
   *********
    *******
     *****
      ***
       *
```