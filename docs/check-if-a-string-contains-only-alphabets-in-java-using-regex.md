# 使用 Regex

检查字符串是否只包含 Java 中的字母

> 原文:[https://www . geeksforgeeks . org/check-if-a-string-contains-only-alphabets-in-Java-using-regex/](https://www.geeksforgeeks.org/check-if-a-string-contains-only-alphabets-in-java-using-regex/)

给定一个字符串，任务是检查一个字符串是否只包含字母，或者是否在 Java 中使用 Regex。

**示例:**

```java
Input: GeeksforGeeks
Output: True

Input: Geeks4Geeks
Output: False

Input: null
Output: False

```

在本文中，使用**正则表达式逐个检查字符串的字符。**

[正则表达式或正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)是一个定义字符串模式的应用编程接口，可用于搜索、操作和编辑文本。它被广泛用于定义对字符串(如密码)的约束。正则表达式在 **java.util.regex** 包下提供。

Regex

> **^[a-zA-Z]*$**

可用于检查字符串中的字母。 [String.matches()方法](https://www.geeksforgeeks.org/java-lang-string-matches-java/)用于检查字符串是否与给定的正则表达式匹配。

**算法:**

1.  去拿绳子
2.  使用匹配项()将字符串与 Regex 匹配。
3.  返回真匹配

**伪代码:**

```java
public static boolean isStringOnlyAlphabet(String str)
{
    return ((!str.equals(""))
            && (str != null)
            && (str.matches("^[a-zA-Z]*{content}quot;)));
}
```

下面是上述方法的实现:

**程序:**检查只包含字母的字符串

```java
// Java program to check if String contains only Alphabets
// using Regular Expression

class GFG {

    // Function to check String for only Alphabets
    public static boolean isStringOnlyAlphabet(String str)
    {
        return ((str != null)
                && (!str.equals(""))
                && (str.matches("^[a-zA-Z]*{content}quot;)));
    }

    // Main method
    public static void main(String[] args)
    {

        // Checking for True case
        System.out.println("Test Case 1:");

        String str1 = "GeeksforGeeks";
        System.out.println("Input: " + str1);
        System.out.println(
            "Output: "
            + isStringOnlyAlphabet(str1));

        // Checking for String with numeric characters
        System.out.println("\nTest Case 2:");

        String str2 = "Geeks4Geeks";
        System.out.println("Input: " + str2);
        System.out.println(
            "Output: "
            + isStringOnlyAlphabet(str2));

        // Checking for null String
        System.out.println("\nTest Case 3:");

        String str3 = null;
        System.out.println("Input: " + str3);
        System.out.println(
            "Output: "
            + isStringOnlyAlphabet(str3));

        // Checking for empty String
        System.out.println("\nTest Case 4:");

        String str4 = "";
        System.out.println("Input: " + str4);
        System.out.println(
            "Output: "
            + isStringOnlyAlphabet(str4));
    }
}
```

**Output:**

```java
Test Case 1:
Input: GeeksforGeeks
Output: true

Test Case 2:
Input: Geeks4Geeks
Output: false

Test Case 3:
Input: null
Output: false

Test Case 4:
Input: 
Output: false

```

**相关文章:**

*   **[使用 ASCII 值检查字符串是否只包含 Java 中的字母](https://www.geeksforgeeks.org/check-if-a-string-contains-only-alphabets-in-java-using-ascii-values/)**
*   **[使用 Lambda 表达式](https://www.geeksforgeeks.org/check-if-a-string-contains-only-alphabets-in-java-using-lambda-expression/)** 检查字符串是否只包含 Java 中的字母