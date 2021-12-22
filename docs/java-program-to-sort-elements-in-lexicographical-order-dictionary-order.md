# 按照字典顺序(字典顺序)对元素进行排序的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-排序-元素-按字典顺序-字典顺序/](https://www.geeksforgeeks.org/java-program-to-sort-elements-in-lexicographical-order-dictionary-order/)

使用两种方法按**字典顺序**(字典顺序)

1.  Sort the string array: Use any sort technique to sort the array elements.
2.  By using the sort () function that exists in the Arrays class of Java util package.

**例:**

```
Input : Harit Girish Gritav Lovenish Nikhil Harman 
Output: Girish Gritav Harit Harman Lovenish Nikhil

Input : Bob Alice
Output: Alice Bob 

```

**方法 1:** 简单排序技术。

在这种方法中，使用 String 类的 compareToIgnoreCase()方法比较两个字符串。

**使用的功能:**

```
int compareToIgnoreCase(String);

```

**返回值:**

1.  If the 0 parameter is a dictionary string equal to this string.
2.  If the parameter is a string whose dictionary order is greater than this string, it is less than 0.
3.  If the parameter is a string whose dictionary order is less than the string, it is greater than 0.

一个 java 程序，使用排序技术**:**

## Java

```
// Java Program to Sort Elements in
// Lexicographical Order (Dictionary Order)
import java.io.*;

class GFG {

    // this method sort the string array lexicographically.
    public static void
    sortLexicographically(String strArr[])
    {
        for (int i = 0; i < strArr.length; i++) {
            for (int j = i + 1; j < strArr.length; j++) {
                if (strArr[i].compareToIgnoreCase(strArr[j])
                    > 0) {
                    String temp = strArr[i];
                    strArr[i] = strArr[j];
                    strArr[j] = temp;
                }
            }
        }
    }

    // this function prints the array passed as argument
    public static void printArray(String strArr[])
    {
        for (String string : strArr)
            System.out.print(string + " ");
        System.out.println();
    }

    public static void main(String[] args)
    {
        // Initializing String array.
        String stringArray[]
            = { "Harit",    "Girish", "Gritav",
                "Lovenish", "Nikhil", "Harman" };

        // sorting String array lexicographically.
        sortLexicographically(stringArray);

        printArray(stringArray);
    }
}
```

**输出**

```
Girish Gritav Harit Harman Lovenish Nikhil 

```

**时间复杂度:** O(n <sup>2</sup> ，其中 n 是数组的大小。

**通过使用**数组来接近 2:**. sort()**

在这种方法中，使用了 [java.utils.Arrays](https://www.geeksforgeeks.org/array-class-in-java/) 类方法中的 sort()方法。

**使用的功能:**

```
Arrays.sort(stringArray, String.CASE_INSENSITIVE_ORDER);

// First Parameter : Name of Array
// Second Parameter: Special command to ignore case while sorting.
```

一个 java 程序使用 Arrays.sort()方法**:**

## Java

```
// Java Program to Sort Elements in
// Lexicographical Order (Dictionary Order)
import java.io.*;
import java.util.Arrays;

class GFG {
    // this function prints the array passed as argument
    public static void printArray(String strArr[])
    {
        for (String string : strArr)
            System.out.print(string + " ");
        System.out.println();
    }
    public static void main(String[] args)
    {
        // Initializing String array.
        String stringArray[]
            = { "Harit",    "Girish", "Gritav",
                "Lovenish", "Nikhil", "Harman" };

        // sorting String array in Lexicographical Order.
        // Ingonring the case of string.
        Arrays.sort(stringArray,
                    String.CASE_INSENSITIVE_ORDER);

        // printing String array after sorting.
        printArray(stringArray);
    }
}
```

**输出**

```
Girish Gritav Harit Harman Lovenish Nikhil 

```

**时间复杂度:** O ( n log n)