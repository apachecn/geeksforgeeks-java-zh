# 计算字符串中元音和辅音总数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-计算字符串中元音和辅音的总数/](https://www.geeksforgeeks.org/java-program-to-count-the-total-number-of-vowels-and-consonants-in-a-string/)

给定一个字符串，计算这个字符串中元音和辅音的总数。假设字符串可能只包含特殊字符、空格或所有字符的组合。其思想是迭代字符串并检查该字符是否存在于引用字符串中。如果字符出现在参考中，则将元音数量增加 1，否则，将辅音数量增加 1。

**示例:**

```java
Input : String = "GeeksforGeeks"
Output: Number of Vowels = 5
        Number of Consonants = 8

Input : String = "Alice"
Output: Number of Vowels = 3
        Number of Consonants = 2
```

**进场:**

1.  创建两个变量 forward 和 cons，并用 0 初始化它们。
2.  开始字符串遍历。
3.  如果第一个字符是元音，那么在誓言变量中增加 1。
4.  否则，如果字符是辅音，那么 cons 变量增加 1。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Count Total Number of Vowels
// and Consonants in a String

// Importing all utility classes
import java.util.*;

// Main class
class GFG {

     // Method 1
    // To prints number of vowels and consonants
    public static void count(String str)
    {
        // Initially initializing elements with zero
        // as till now we have not traversed 
        int vow = 0, con = 0;

        // Declaring a reference String
        // which contains all the vowels
        String ref = "aeiouAEIOU";

        for (int i = 0; i < str.length(); i++) {

            // Check for any special characters present
            // in the given string
            if ((str.charAt(i) >= 'A'
                 && str.charAt(i) <= 'Z')
                || (str.charAt(i) >= 'a'
                    && str.charAt(i) <= 'z')) {
                if (ref.indexOf(str.charAt(i)) != -1)
                    vow++;
                else
                    con++;
            }
        }

        // Print and display number of vowels and consonants
        // on console
        System.out.println("Number of Vowels = " + vow
                           + "\nNumber of Consonants = "
                           + con);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom string as input
        String str = "#GeeksforGeeks";

        // Callin gthe method 1
        count(str);
    }
}
```

**Output**

```java
Number of Vowels = 5
Number of Consonants = 8
```

> **时间复杂度:** O(n)这里，n 是字符串的长度。