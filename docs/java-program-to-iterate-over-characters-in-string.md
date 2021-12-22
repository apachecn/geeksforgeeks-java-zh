# Java 程序迭代字符串中的字符

> 原文:[https://www . geeksforgeeks . org/Java-程序迭代字符串中的字符/](https://www.geeksforgeeks.org/java-program-to-iterate-over-characters-in-string/)

给定长度为 **N** 的字符串 **str** ，任务是遍历该字符串并使用 java 打印给定字符串的所有字符。

插图:

```
Input  : str = “GeeksforGeeks”
Output : G e e k s f o r G e e k s
```

```
Input  : str = "GfG"
Output : G f G
```

**方法:**

1.  用于循环(简单方法)
2.  使用迭代器(最佳方法)

**方法 1:** 用于循环

解决这个问题的最简单或者说是最天真的方法是使用变量“**I”**使用循环迭代到字符串的长度，然后打印字符串中每个字符的值。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Iterate Over Characters in String

// Class 1
// Main class
// To iterate over characters
class GFG {

    // Method 1
    // To traverse the string and
    // print the characters of the string
    static void getChar(String str)
    {

        // Traverse the string using for loop
        for (int i = 0; i < str.length(); i++) {

            // Printing the current character
            System.out.print(str.charAt(i));

            // Printing a space after each letter
            System.out.print(" ");
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating a String variable to store the string
        String str = "GeeksforGeeks";

        // Calling the getChar method
        getChar(str);
    }
}
```

**Output**

```
G e e k s f o r G e e k s 
```

> 时间复杂度为 **O(N)** ，空间复杂度为 **O(1)**

**方法 2:** 使用迭代器

可以使用迭代器遍历字符串。我们将从 java.text 包中导入**特征描述符**和**字符串特征描述符**类

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Iterate Over Characters in String

// Importing input output classes
import java.io.*;
// Importing CharacterIterator and StringCharacterIterator
// classes from java.text package
import java.text.CharacterIterator;
import java.text.StringCharacterIterator;

// Main class
// To iterate over characters
class GFG {

    // Method 1
    // To traverse the string and
    // print the characters of the string
    static void getChar(String str)
    {

        // Creating a CharacterIterator variable
        CharacterIterator itr
            = new StringCharacterIterator(str);

        // Iterating using while loop
        while (itr.current() != CharacterIterator.DONE) {

            // Print the current character
            System.out.print(itr.current());

            // Print a space after each letter
            System.out.print(" ");

            // Getting the next input from the user
            // using the next() method
            itr.next();
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Creating a String variable to store the string
        String str = "GfG";

        // Calling the getChar method
        getChar(str);
    }
}
```

**Output**

```
G f G 
```

> **时间复杂度:** O(N)，空间复杂度为 O(1)量级