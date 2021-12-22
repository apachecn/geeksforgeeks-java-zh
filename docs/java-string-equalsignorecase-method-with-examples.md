# Java 字符串 equalsIgnoreCase()方法示例

> 原文:[https://www . geesforgeks . org/Java-string-equalsignorace-method-with-examples/](https://www.geeksforgeeks.org/java-string-equalsignorecase-method-with-examples/)

[字符串类](https://www.geeksforgeeks.org/string-class-in-java/) 的***equalsignorase()方法*** 比较两个字符串，而不管字符串的大小写。此方法返回一个布尔值，如果参数不为空并且表示忽略大小写的等效字符串，则为 true，否则为 false。

**语法:**

```java
str2.equalsIgnoreCase(str1);
```

> **注意:**这里 str1 和 str2 都是我们需要比较的字符串。

**参数:**应该比较的字符串。

**返回类型:**一个布尔值，如果参数不为空，并且它表示忽略大小写的等效字符串，则为真，否则为假。

**插图:**

```java
Input : str1 = "pAwAn";
        str2 = "PAWan"
        str2.equalsIgnoreCase(str1);
Output :true
```

```java
Input : str1 = "powAn";
        str2 = "PAWan"
        str2.equalsIgnoreCase(str1);
Output :false
Explanation: powan and pawan are different strings. 
```

> **注意:** str1 是需要和 str2 比较的字符串。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate equalsIgnoreCase() method

// Importing required classes
import java.lang.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declaring and initializing strings to compare
        String str1 = "GeeKS FOr gEEks";
        String str2 = "geeKs foR gEEKs";
        String str3 = "ksgee orF geeks";

        // Comparing strings
        // If we ignore the cases
        boolean result1 = str2.equalsIgnoreCase(str1);

        // Both the strings are equal so display true
        System.out.println("str2 is equal to str1 = "
                           + result1);

        // Even if we ignore the cases
        boolean result2 = str2.equalsIgnoreCase(str3);

        // Both the strings are not equal so display false
        System.out.println("str2 is equal to str3 = "
                           + result2);
    }
}
```

**Output**

```java
str2 is equal to str1 = true
str2 is equal to str3 = false
```