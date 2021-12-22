# 如何在 Java 中使用正则表达式验证标识符

> 原文:[https://www . geesforgeks . org/如何使用 java 正则表达式验证标识符/](https://www.geeksforgeeks.org/how-to-validate-identifier-using-regular-expression-in-java/)

给定一个字符串 **str** ，任务是使用[正则表达式](https://www.geeksforgeeks.org/write-regular-expressions/)检查该字符串是否是有效的[标识符](https://www.geeksforgeeks.org/java-identifiers/)。
定义 Java 标识符的有效规则是:

*   必须以小写字母**【A-Z】**或大写字母**【A-Z】**或下划线 **(_)** 或美元符号 **($)** 开头。
*   应该是单个单词，不允许有空格。
*   它不应该以数字开头。

**例:**

> **输入:**str = $ geeks 123“
> **输出:**真
> **说明:**给定的字符串满足上述所有条件。
> **输入:**str = $ gee ks 123 "
> **输出:** False
> **说明:**给定的字符串包含空格，因此不是有效的标识符。
> **输入:**str = " 1 geeks { content } # x201；
> **输出:**假
> **说明:**给定字符串以数字开头，因此不是有效的标识符。

**方法:**这个问题可以用[正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)来解决。

1.  去拿绳子。
2.  创建一个正则表达式来检查有效的标识符。

```
regex = "^([a-zA-Z_$][a-zA-Z\\d_$]*){content}quot;;
```

3.其中:

*   **^** 代表字符串的起始字符。
*   **[a-zA-Z_$]** 表示，字符串仅以小写字母或大写字母或下划线(_)或美元符号($)开头。>/Li>T2】
*   **[a-zA-Z\\d_$]*** 表示，字符串可以是字母数字或 uderscore(_)或美元符号($)在字符串的第一个字符之后。它包含一个或多个时间。
*   **$** 代表字符串的结尾。

4.将给定的字符串与 Regex 匹配。在 Java 中，这可以使用 [Pattern.matcher()](https://www.geeksforgeeks.org/pattern-matchercharsequence-method-in-java-with-examples/) 来完成。

5.如果字符串与给定的正则表达式匹配，则返回 true，否则返回 false。

以下是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to validate the
// identifiers using Regular Expression.

import java.util.regex.*;

class GFG {

    // Function to validate the identifier.
    public static boolean
    isValidIdentifier(String identifier)
    {

        // Regex to check valid identifier.
        String regex = "^([a-zA-Z_$][a-zA-Z\\d_$]*){content}quot;;

        // Compile the ReGex
        Pattern p = Pattern.compile(regex);

        // If the identifier is empty
        // return false
        if (identifier == null) {
            return false;
        }

        // Pattern class contains matcher() method
        // to find matching between given identifier
        // and regular expression.
        Matcher m = p.matcher(identifier);

        // Return if the identifier
        // matched the ReGex
        return m.matches();
    }

    // Driver Code.
    public static void main(String args[])
    {

        // Test Case 1:
        String str1 = "$geeks123";
        System.out.println(isValidIdentifier(str1));

        // Test Case 2:
        String str2 = "$gee ks123";
        System.out.println(isValidIdentifier(str2));

        // Test Case 3:
        String str3 = "1geeks{content}quot;;
        System.out.println(isValidIdentifier(str3));
    }
}
```

**Output:** 

```
true
false
false
```