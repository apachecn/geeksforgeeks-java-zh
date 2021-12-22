# 检查字符串是否为回文的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-check-字符串是否是回文/](https://www.geeksforgeeks.org/java-program-to-check-whether-a-string-is-a-palindrome/)

如果我们从左到右或从右到左开始读，如果字符串相同，则称它为回文。所以让我们考虑一个字符串“**str”**，现在的任务只是找出与它相反的字符串是否与其相同。

插图:

```
Input : str = "abba" 
Output: Yes
```

```
Input : str = "geeks"
Output: No  
```

**进场:**我们的进场将会是，最初，我们会拿两个指针 **i** 指向绳子的起点， **j** 指向绳子的终点。当 **i < j** 时，继续增加 **i** 和减少 **j** ，并在每一步检查这些指针处的字符是否相同。如果不是，那么这个字符串就不是回文了。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to check whether a
// string is a Palindrome
// Using two pointing variables

// Main class
public class GFG {

    // Method
    // Returning true if string is palindrome
    static boolean isPalindrome(String str)
    {

        // Pointers pointing to the beginning
        // and the end of the string
        int i = 0, j = str.length() - 1;

        // While there are characters to compare
        while (i < j) {

            // If there is a mismatch
            if (str.charAt(i) != str.charAt(j))
                return false;

            // Increment first pointer and
            // decrement the other
            i++;
            j--;
        }

        // Given string is a palindrome
        return true;
    }

    // Method 2
    // main driver method
    public static void main(String[] args)
    {
        // Input string
        String str = "geeks";

        // passing bool function till holding true
        if (isPalindrome(str))

            // It is a palindrome
            System.out.print("Yes");
        else

            // Not a palindrome
            System.out.print("No");
    }
}
```

**Output:** 

```
No
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to check Whether the String is Palindrome
// or Not

// Main class
class GFG {

    // Method 1
    // Returns true if string is a palindrome
    static boolean isPalindrome(String str)
    {

        // Pointers pointing to the beginning
        // and the end of the string
        int i = 0, j = str.length() - 1;

        // While there are characters to compare
        while (i < j) {

            // If there is a mismatch
            if (str.charAt(i) != str.charAt(j))
                return false;

            // Increment first pointer and
            // decrement the other
            i++;
            j--;
        }

        // Given string is a palindrome
        return true;
    }

    // Main driver method
    public static void main(String[] args)
    {
        String str = "geeks";
        String str2 = "racecar";

        // For string 1
        System.out.print("String 1 :");

        if (isPalindrome(str))
            System.out.print("It is a palindrome");
        else
            System.out.print("It is not a palindrome");

        // new line for better readability
        System.out.println();

        // For string 2
        System.out.print("String 1 :");
        if (isPalindrome(str2))
            System.out.print("It is a palindrome");
        else
            System.out.print("It is not a palindrome");
    }
}
```

**Output**

```
String 1 :It is not a palindrome
String 1 :It is a palindrome
```