# 查找一个字符串的所有回文子字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-all-回文-字符串的子字符串/](https://www.geeksforgeeks.org/java-program-to-find-all-palindromic-sub-strings-of-a-string/)

给定一个字符串，任务是统计给定字符串中的所有回文子串。

```
Input        : aba
Output : 4
Explanation : All palindrome substring are : "aba" , "a" , "b", "a"

Input : TENET
Output : 7
Explanation : All palindrome sub-string are : "T" , "E" , "N", "E", "T" , "ENE" , "TENET"
```

**进场:**

1.  从给定的字符串中获取子字符串。
2.  现在检查子串是否是回文。
3.  如果子串是回文，则计数增加 1，否则计数不增加。
4.  返回表示子字符串数量的计数。
5.  打印并显示在控制台上。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Find all palindromic sub-strings 
// of a given string

// Importing input output classes
import java.io.*;

// Main class
// To check for pallindromic sub-strings
public class GFG {

    // Method 1
    // To check for substring
    public static boolean check(String subS)
    {
        int size = subS.length();

        // Iterating over string till midway to
        // check pallindromic behavior
        for (int i = 0; i < size / 2; i++) {

            if (subS.charAt(i)
                != subS.charAt(size - i - 1)) {

                // Non-pallindromic behavior
                return false;
            }
        }

        // Pallindromic behavior
        return true;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Custom input string
        String str = "MALAYALAM";

        int count = 0;

        // Outer loop iterating over input string
        for (int i = 0; i < str.length(); i++) {

            // Inner loop iterating from current starting
            // character of outer loop current starting
            // character
            for (int j = i; j < str.length(); j++) {

                // Getting the substrings
                String subString = str.substring(i, j + 1);

                // Checking whether the substring is
                // pallindrome
                if (check(subString)) {

                    // Increment the count only if
                    // substring is pallindrome
                    count++;
                }
            }
        }

        // Print and display the number of substrings that
        // are pallindromic
        System.out.println(
            "No.of palindromic substrings in the given string are "
            + count);
    }
}
```

**Output**

```
No.of palindromic substrings in the given string are 15
```