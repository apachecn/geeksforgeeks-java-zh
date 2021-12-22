# 使用正则表达式

从较大字符串中提取单引号括起来的字符串的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-program-to-extract-a-single-quote-括起来-string-from-a-big-string-use-regex/](https://www.geeksforgeeks.org/java-program-to-extract-a-single-quote-enclosed-string-from-a-larger-string-using-regex/)

**问题陈述:**给定一个字符串，使用 Java Regex 提取用单引号(')括起来的子字符串。

Java regex 是一个用正则表达式进行模式匹配的 API。*‘Java . util . regex’*是一个用于 <matching character="" sequences="" against="" patterns="" specified="" by="" regular="" expressions="" where="" the="" instance="" of="" pattern="" class="" represents="" a="" expression="" while="" instances="" matcher="" is="" used="" to="" match="" sequence="" given="" pattern.="" input="" provided="" matches="" via="" target="_blank" rel="noopener noreferrer nofollow" href="https://docs.oracle.com/javase/8/docs/api/java/lang/CharSequence.html">CharSequence <接口的类，以便支持与来自各种输入源的字符进行匹配。不允许将空参数传递给任何类或接口，因为它会抛出一个名为[<nullpointerexception a=""><. hence="" it="" can="" be="" concluded="">“Java . util . regex”的异常，该异常包含如下接口和类:</nullpointerexception>](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)</matching>

> [*   连接
>     1.  匹配结果:匹配操作的结果](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)
> *   [班级](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)
>     [](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)
>     2.  [匹配器:通过解释](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)[模式](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html)对[字符序列](https://docs.oracle.com/javase/8/docs/api/java/lang/CharSequence.html)进行匹配操作的引擎。
>     3.  模式:正则表达式的编译表示。

**插图:**

```
Input  : "Out of this String required only is 'Geeks for Geeks' only'"
Output : Geeks for Geeks

Input  : "The data wanted is'Java Regex'"
Output : Java Regex
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate extracting
// substring enclosed in single quotes

// Importing Matcher and Pattern class
// from regex class of java.util package
// Importing input output classes
import java.io.*;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Custom input
        String string1
            = "Out of this String I want 'Geeks for Geeks' only";

        // Desired custom output
        String string2
            = "The data that I want is'Java Regex'";

        // Paranthesis indicate it is a group and signifies
        // it can have substring enclosed in single quote
        Pattern p = Pattern.compile(".*'([^']*)'.*");

        // This method returns a pattern object

        // Calling matcher() method of pattern object
        // and passing input character sequence
        Matcher m1 = p.matcher(string1);
        Matcher m2 = p.matcher(string2);

        // Printing complete entered string 1
        System.out.println("String to be extracted : "
                           + string1);

        // Condition check using matches() method which
        // looks out for content if any in single quote
        if (m1.matches()) {

            // Print the required sub-string
            System.out.println("Extracted part         : "
                               + m1.group(1));
        }

        // New line
        System.out.println();

        // Printing complete entered string 2
        System.out.println("String to be extracted : "
                           + string2);

        // Condition check using matches() method which
        // looks out for content if any in single quote
        if (m2.matches()) {

            // Print the required sub-string
            System.out.println("Extracted part         : "
                               + m2.group(1));
        }
    }
}
```

**Output**

```
String to be extracted : Out of this String I want 'Geeks for Geeks' only
Extracted part         : Geeks for Geeks

String to be extracted : The data that I want is'Java Regex'
Extracted part         : Java Regex
```