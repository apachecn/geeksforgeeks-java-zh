# 使用正则表达式将字符串转换为字符串数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-convert-string-to-string-array-use-正则表达式/](https://www.geeksforgeeks.org/java-program-to-convert-string-to-string-array-using-regular-expression/)

[正则表达式或 Regex](https://www.geeksforgeeks.org/regular-expressions-in-java/) (简而言之)是一个定义字符串模式的 API，可用于在 Java 中搜索、操作和编辑字符串。电子邮件验证和密码是少数几个广泛使用 Regex 来定义约束的字符串领域。正则表达式在 [*java 下提供。*util . regex 包](https://www.geeksforgeeks.org/regular-expressions-in-java/)。这包括 3 个类和 1 个接口。因此，简而言之，我们可以得出结论，java 的正则表达式用于从字符序列中查找、匹配和提取数据。

**方法:**我们可以使用 String 类和正则表达式的拆分方法将 String 转换为 String 数组。

1.  First, we use regular expressions.
2.  Split the string and now store this in an array.
3.  Print and display on the console.

**法:**

1.  Use *split ()* method only.
2.  Use? ! Regular expression with *split ()* method

**方法 1:** 仅使用*分裂()*方法

**示例:**

## Java

```
// Java program to demonstrate how to convert String to
// String Array using Regular Expression in Java

// Importing all classes from
// java.util package
import java.util.*;

// Importing Matcher class that searches through a text for
// multiple occurences of a regular expression 
import java.util.regex.Matcher;

// Importing Pattern class
import java.util.regex.Pattern;

// Importing Pattern class to compile regex

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Random string input
        String gfg = "Welcome, to, GFG";

        // Splitting of string into characters and
        // storing it in an array string
        // separated by comma in between characters
        String[] str = gfg.split(",");

        // Traversing the above array
        // using for each loop
        for (String s : str) {

            // Print the characters of the array
            // formed from input string
            System.out.println(s);
        }
    }
}
```

**输出**

```
Welcome
 to
 GFG
```

**方法二:**使用？！^'正则表达式连同*分裂()*方法

**进场:**

用拆分法，我们就用**？！^** 分裂字符串的正则表达式。并提取字符序列的数据。

*   **？ !** -indicates negative foresight.
*   -This is the beginning of the string.

**示例:**

## Java

```
// Java program to demonstrate how to convert String to
// String Array using Regular Expression in Java

// Importing all classes from
// java.util package
import java.util.*;

// Importing Matcher and Pattern classes from
// java.util.regex package because

// Matcher Class searches through a text for
// multiple occurences of a regular expression
import java.util.regex.Matcher;

// Pattern Class to compile regex
import java.util.regex.Pattern;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Random input string
        String gfg = "Welcome, to, GFG";

        // Split the above input string
        // using split() method and
        // store the input string elements as an array
         String[] str = gfg.split("(?!^)");

        // Print all the elements of an array
        System.out.println(Arrays.toString(str));
    }
}
```

**输出**

```
[W, e, l, c, o, m, e, ,,  , t, o, ,,  , G, F, G]
```