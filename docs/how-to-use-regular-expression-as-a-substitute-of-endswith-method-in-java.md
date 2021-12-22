# 如何用正则表达式替代 Java 中的 endsWith()方法？

> 原文:[https://www . geesforgeks . org/如何使用正则表达式替代 java 中的 endswith-method/](https://www.geeksforgeeks.org/how-to-use-regular-expression-as-a-substitute-of-endswith-method-in-java/)

所以主要讨论什么是 endsWith()方法，所以它是 String 类的一个方法，检查字符串是否以指定的后缀结尾。此方法返回一个布尔值 true 或 false。

**语法:**

```
public boolean endsWith(String suff)      
```

**参数:**指定后缀部分

**Return:** 布尔值，在 java 这里我们只有真和假。

**方法:**

我们可以用正则表达式/匹配来代替 Java 中的 ***endsWith()方法***

1.  使用正则表达式
2.  使用匹配

**方法 1:** 使用正则表达式

正则表达式(简称 Regex)是一个定义字符串模式的应用编程接口，可用于在 Java 中搜索、操作和编辑字符串。电子邮件验证和密码是字符串的几个领域，Regex 被广泛用于定义约束。正则表达式在 java.util.regex 包下提供。这包括 3 个类和 1 个接口。 [java.util.regex 包](https://www.geeksforgeeks.org/regular-expressions-in-java/)主要由以下三个类组成，如下表所示:

*   模式
*   制榫机
*   PatternSyntaxException

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate use of Regular Expression
// as substitute of endsWith() method

// Importing required classes
import java.util.regex.Matcher;
import java.util.regex.Pattern;

// Main class
public class Geek {

    // Main driver method
    public static void main(String args[])
    {

        // Declaring and initialising string
        String Str = new String("Welcome to geeksforgeeks");

        // Display message
        System.out.print(
            "Check whether string ends with Welcome using endsWith : ");

        // Using endWith() method
        System.out.println(Str.endsWith("geeks"));

        // Creating Pattern and matcher classes object
        Pattern pattern = Pattern.compile(".*geeks");
        Matcher m = pattern.matcher(Str);

        // Checking whether string ends with specific word
        // or nor and returning the boolean value
        // using ? operator and find() method
        System.out.print(
            "Check whether string ends with Welcome using Regex: ");
        System.out.println(m.find() ? "true" : "false");
    }
}
```

**Output**

```
Check whether string ends with Welcome using endsWith : true
Check whether string ends with Welcome using Regex: true
```

**方法 2:** 使用火柴

[*String.matches()*](https://www.geeksforgeeks.org/java-lang-string-matches-java/) 方法告诉这个字符串是否匹配给定的正则表达式。调用表单的这个方法会产生与表达式 Pattern.matches(正则表达式，字符串)完全相同的结果。

**语法:**

```
public boolean matches(String regex);
```

**参数:**该字符串要匹配的正则表达式。

**返回值:**当且仅当该字符串与给定的正则表达式匹配时，该方法返回 true。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate use of Matches
// as substitute of endsWith() method

// Importing all utility classes
import java.util.*;

// Main class
public class Geek {

    // Main driver method
    public static void main(String args[])
    {

        // Initialising String
        String Str = new String("Welcome to geeksforgeeks");

        // Display message for better readability
        System.out.print(
            "Check whether string starts with Welcome using endsWith : ");
        // Using endsWith() to end with specific word
        System.out.println(Str.endsWith("geeks"));

        // Display message for better readability
        System.out.print(
            "Check whether string starts with Welcome using Matches: ");
        // Now checking whether it matches with
        // above defined specific word
        System.out.println(Str.matches("(.*)geeks"));
    }
}
```

**Output**

```
Check whether string starts with Welcome using endsWith : true
Check whether string starts with Welcome using Matches: true
```