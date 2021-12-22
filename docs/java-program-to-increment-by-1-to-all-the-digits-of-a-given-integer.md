# 给定整数的所有数字加 1 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序对给定整数的所有数字进行 1 的增量/](https://www.geeksforgeeks.org/java-program-to-increment-by-1-to-all-the-digits-of-a-given-integer/)

给定一个整数，任务是生成一个 Java 程序，将给定整数的所有数字递增 1。

**例:**

```java
Input: 12345
Output: 23456

Input: 110102
Output: 221213

```

**方法 1:**

在这种方法中，我们将创建一个与输入长度相同的数字，并且其中只包含 1。然后我们会添加它们。

1.  取整数输入。
2.  找到它的长度，然后生成只包含 1 的数字作为长度的数字。
3.  将两个数字相加。
4.  打印结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Increment by 1 All the Digits of a given
// Integer

// Importing Libraries
import java.util.*;
import java.io.*;

class GFG {
    // Main function
    public static void main(String[] args)
    {
        // Declaring the number
        int number = 110102;

        // Converting the number to String
        String string_num = Integer.toString(number);

        // Finding the length of the number
        int len = string_num.length();

        // Declaring the empty string
        String add = "";

        // Generating the addition string
        for (int i = 0; i < len; i++) {
            add = add.concat("1");
        }

        // COnverting it to Integer
        int str_num = Integer.parseInt(add);

        // Adding them and displaying the result
        System.out.println(number + str_num);
    }
}
```

**Output**

```java
221213

```

**方法 2:**

在这种方法中，我们将取一个值为 1 的整数变量，将该变量乘以 10，并继续将该变量与数字相加，直到两者具有相同的长度。

1.  Enter as an integer.
2.  Add a value of 1 to the input.
3.  Multiply 1 by 10 and add again.
4.  Repeat steps 2 and 3 until they are the same length.
5.  Print the results.

## Java

```java
// Java Program to Increment by 1 All the Digits of a given
// Integer

// Importing Libraries
import java.util.*;
import java.io.*;

class GFG {
    // Main function
    public static void main(String[] args)
    {
        // Declaring the number
        int number = 110102;
        // Declaring another variable with value 1
        int add = 1;

        for (int i = 0; i < String.valueOf(number).length();
             i++) {
            // Adding variable add  and number
            number = number + add;

            // Multiplying value of the add with 10
            add = add * 10;
        }
        // Printing result
        System.out.println(number);
    }
}
```

**输出**

```java
221213

```

**时间复杂度:**O(l)**l**是整数的长度。

**空间复杂度:** O(1)