# 在 Java 中使用正则表达式计算给定字符的出现次数

> 原文:[https://www . geeksforgeeks . org/count-给定字符的出现次数-使用-regex-in-java/](https://www.geeksforgeeks.org/count-occurrences-of-a-given-character-using-regex-in-java/)

给定一个字符串和一个字符，任务是使用 [Regex](https://www.geeksforgeeks.org/regex-regular-expression-in-c/) 创建一个函数来计算字符串中给定字符的出现次数。

**示例:**

```
Input: str = "geeksforgeeks", c = 'e'
Output: 4
'e' appears four times in str.

Input: str = "abccdefgaa", c = 'a' 
Output: 3
'a' appears three times in str.
```

#### 正则表达式

正则表达式或正则表达式是一个定义字符串模式的应用编程接口，可用于在 Java 中搜索、操作和编辑字符串。电子邮件验证和密码是字符串的几个领域，Regex 被广泛用于定义约束。正则表达式在 **java.util.regex** 包下提供。

#### **方法–**在 Java Regex 中使用 Matcher.find()方法

*   获取要匹配的字符串
*   使用 [Matcher.find()函数(在 Java 中)](https://www.geeksforgeeks.org/matcher-find-method-in-java-with-examples/)查找给定字符的所有匹配项
*   对于每个找到的事件，将计数器增加 1

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to count occurrences
// of a character using Regex

import java.util.regex.*;

class GFG {

    // Method that returns the count of the given
    // character in the string
    public static long count(String s, char ch)
    {

        // Use Matcher class of java.util.regex
        // to match the character
        Matcher matcher
            = Pattern.compile(String.valueOf(ch))
                  .matcher(s);

        int res = 0;

        // for every presence of character ch
        // increment the counter res by 1
        while (matcher.find()) {
            res++;
        }

        return res;
    }

    // Driver method
    public static void main(String args[])
    {
        String str = "geeksforgeeks";
        char c = 'e';
        System.out.println("The occurrence of " + c + " in "
                           + str + " is " + count(str, c));
    }
}
```

**Output**

```
The occurrence of e in geeksforgeeks is 4
```

**相关文章:**

*   [程序计数](https://www.geeksforgeeks.org/program-count-occurrence-given-character-string/) [字符串中给定字符的出现次数](https://www.geeksforgeeks.org/program-count-occurrence-given-character-string/)
*   [使用 Java 中的 Stream API 计算字符串中给定字符的出现次数](https://www.geeksforgeeks.org/count-occurrence-of-a-given-character-in-a-string-using-stream-api-in-java/)