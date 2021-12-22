# 用正则表达式说明转义字符的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-instruction-转义字符-in-regex/](https://www.geeksforgeeks.org/java-program-to-illustrate-escaping-characters-in-regex/)

点(.)等特殊字符。)、哈希(#)等。，它对正则表达式有特殊意义，需要在正则表达式中转义以匹配。例如，如果点(。)在正则表达式中不转义，它匹配任何单个字符，从而给出不明确的结果。

**方法:**

在 Java Regex 中，字符可以通过两种方式进行转义，如下所列，我们将深入讨论:

1.  使用\Q 和\E 进行转义
2.  使用反斜杠(\\)进行转义

**方法 1:** 使用\Q 和\E 进行转义

*   我们可以使用\Q 和\E 转义序列来转义字符。
*   \Q 标记转义序列的开始，而\E 标记转义序列的结束。
*   \Q 和\E 之间的任何字符都被转义。
*   通常用于转义多个字符。

#### **实施:**

在下面的源代码中，Regex 模式 p 被转义为点(。)运算符，而模式 p1 对于点(。).因此，模式 p 仅与字符串 s 匹配，而模式 p1 与字符串 s 和 s1 都匹配。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Escaping Characters in Java
// Regex Using \Q and \E for escaping

// Importing required classes
import java.io.*;
import java.util.regex.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Sample strings as inputs
        String s = "Geeks.forGeeks";
        String s1 = "GeeksforGeeks";

        // Creating object of Pattern class

        // 1\. Patterns with dot escaped
        Pattern p = Pattern.compile("\\Q.\\E");

        // 2, Pattern without dot escaped
        Pattern p1 = Pattern.compile(".");

        // Matchers for each pattern string combination
        Matcher m = p.matcher(s);
        Matcher m1 = p.matcher(s1);
        Matcher m2 = p1.matcher(s);
        Matcher m3 = p1.matcher(s1);

        // Print and display whether p,p1 matches
        // or not via boolean true false
        System.out.println("p matches s: " + m.find());
        System.out.println("p matches s1: " + m1.find());
        System.out.println("p1 matches s: " + m2.find());
        System.out.println("p1 matches s1: " + m3.find());
    }
}
```

**Output**

```
p matches s: true
p matches s1: false
p1 matches s: true
p1 matches s1: true
```

**方法 2:** 使用反斜杠(\\)进行转义

*   我们可以使用反斜杠来转义字符。
*   我们需要两个反斜杠，因为反斜杠本身是一个字符，需要转义。
*   \\之后的字符被转义。
*   它通常用于转义字符串末尾的字符。

**实施:**

在下面的源代码中，正则表达式模式 **p** 被转义为点(**)。**)运算符，而模式 **p1** 对于点(**)没有转义。**)。因此图案 **p** 仅与弦 **s** 匹配，而图案 **p1** 与弦 **s** 和 **s1** 都匹配。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
/*package whatever //do not write package name here */

import java.io.*;
import java.util.regex.*;

class GFG {
    public static void main (String[] args) {

        String s="Geeks.forGeeks";//sample strings
        String s1="GeeksforGeeks";
          //patterns with dot escaped
        Pattern p=Pattern.compile("\\.");
          // pattern without dot escaped
          Pattern p1=Pattern.compile(".");
          //matchers for each pattern string combination
        Matcher m=p.matcher(s);
          Matcher m1=p.matcher(s1);
          Matcher m2=p1.matcher(s);
          Matcher m3=p1.matcher(s1);
          //outputs
        System.out.println("p matches s: "+m.find());
          System.out.println("p matches s1: "+m1.find());
          System.out.println("p1 matches s: "+m2.find());
          System.out.println("p1 matches s1: "+m3.find());
    }
}
```

**输出:**

```
p matches s: true
p matches s1: false
p1 matches s: true
p1 matches s1: true
```