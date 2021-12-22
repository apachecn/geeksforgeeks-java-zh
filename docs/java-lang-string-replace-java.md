# Java 中的 Java.lang.String.replace()

> 原文:[https://www . geesforgeks . org/Java-lang-string-replace-Java/](https://www.geeksforgeeks.org/java-lang-string-replace-java/)

此方法搜索指定的字符串或指定的值，或者一个正则表达式，根据该表达式具有相同的建议，返回一个带有相关字符的新字符串。替换()方法的字符串包含三个变体这里是**三个**变体的**替换()**方法。

String.replace()经常使用 3 种类型，这也有助于解决问题。

*   replace
*   Replace All ()
*   Replace First ()

**#1:** 字符串。替换()

该方法**返回**一个新的字符串，该字符串是用新字符替换字符串中所有出现的旧字符而得到的。

**语法:**

```java
public String replace(char oldch, char newch)
```

**参数:**

*   Old role
*   New role

**返回类型:**

它通过用 newch 替换 oldch 的每一次出现来返回从该字符串派生的字符串。

**示例**

## Java

```java
// Java code to demonstrate the
// Working of  replace() method

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Declaring and initialising custom input string
        String Str = new String("Welcome to geeksforgeeks");

        // Using replace to replace characters
        System.out.print("After replacing all o with T : ");
        System.out.println(Str.replace('o', 'T'));

        // Using replace to replace characters
        System.out.print("After replacing all e with D : ");
        System.out.println(Str.replace('e', 'D'));
    }
}
```

**输出**

```java
After replacing all o with T : WelcTme tT geeksfTrgeeks
After replacing all e with D : WDlcomD to gDDksforgDDks
```

**2:**字符串 replaceAll()

此方法用给定的 replace_str 替换与给定正则表达式匹配的字符串的每个子字符串。

**语法:**

```java
public String replaceAll(String regex, String replace_str)
```

参数:

*   The regular expression to match the string.
*   Find the replaced string to the expression.

```java
Return Value
This method returns the resulting String
```

**示例**

## Java

```java
// Java Program to demonstrate the
// working of  replaceAll()

// Main class
public class rep2 {

    // Main driver method
    public static void main(String args[])
    {

        // Declaring and initialising String
        String Str = new String("Welcome to geeksforgeeks");

        // Display message
        System.out.print("Original String : ");

        // Printing original string
        System.out.println(Str);

        // Display message
        System.out.print(
            "After replacing regex with replace_str : ");

        // Using replaceAll to replace regex
        // with replace_str
        System.out.println(
            Str.replaceAll("(.*)geeks(.*)", "ASTHA TYAGI"));
    }
}
```

**输出**

```java
Original String : Welcome to geeksforgeeks
After replacing regex with replace_str : ASTHA TYAGI
```

**#3:** 字符串替换第一个()

此方法用给定的 replace_str 替换与给定正则表达式匹配的该字符串的第一个子字符串**。**

**语法:**

```java
public String replaceFirst(String regex, String replace_str)
```

**参数**

*   The regular expression to match the string.
*   Found the expression for the replaced string.

**返回类型:**结果字符串

**例:**

## 爪哇

```java
// Java code to demonstrate the
// working of  replaceFirst()
public class rep3 {
   public static void main(String args[]) {

      // Initialising String
      String Str = new String("Welcome to geeksforgeeks");

      // original string
      System.out.print("Original String : " );
      System.out.println(Str);

      // Using replaceFirst to replace regex with replace_str
      // Replaces 1st occurrence of geeks with ASTHA
      System.out.print("After replacing 1st occurrence of regex with replace_str  : " );
      System.out.println(Str.replaceFirst("geeks", "ASTHA"));

   }
}
```

**输出:**

```java
Original String : Welcome to geeksforgeeks
After replacing 1st occurrence of regex with replace_str  : Welcome to ASTHAforgeeks
```

本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。