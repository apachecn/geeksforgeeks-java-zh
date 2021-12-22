# 如何让 Java 正则表达式在 Java 中不区分大小写？

> 原文:[https://www . geesforgeks . org/how-make-Java-正则表达式-不区分大小写-in-java/](https://www.geeksforgeeks.org/how-to-make-java-regular-expression-case-insensitive-in-java/)

在本文中，我们将学习如何在 Java 中使 Java 正则表达式不区分大小写。Java 正则表达式用于从字符序列中查找、匹配和提取数据。默认情况下，Java 正则表达式区分大小写。但是借助正则表达式，我们可以使 Java 正则表达式不区分大小写。有两种方法可以使正则表达式不区分大小写:

1.  **使用不区分大小写标志**
2.  **使用修改器**

**1。使用不区分大小写标志:**模式类的编译方法将不区分大小写标志和模式一起使用，以使表达式不区分大小写。下面是实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrate How to make Java
// Regular Expression case insensitive in Java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

class GFG {
    public static void main(String[] args)
    {

        // String
        String str = "From GFG class. Welcome to gfg.";

        // Create pattern to match along
        // with the flag CASE_INSENSITIVE
        Pattern patrn = Pattern.compile(
            "gfg", Pattern.CASE_INSENSITIVE);

        // All metched patrn from str case
        // insensitive or case sensitive
        Matcher match = patrn.matcher(str);

        while (match.find()) {
            // Print matched Patterns
            System.out.println(match.group());
        }
    }
}
```

**Output**

```
GFG
gfg
```

**2。使用修饰语:**那个“**？用于使 Java 正则表达式不区分大小写的修饰符。因此，为了使 Java 正则表达式不区分大小写，我们将模式与“**”一起传递？i "** 修饰符，使其不区分大小写。下面是实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrate How to make Java
// Regular Expression case insensitive in Java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

class GFG {
    public static void main(String[] args)
    {

        // String
        String str = "From GFG class. Welcome to gfg.";

        // Create pattern to match along
        // with the ?i modifier
        Pattern patrn = Pattern.compile("(?i)gfg");

        // All metched patrn from str case
        // insensitive or case sensitive
        Matcher match = patrn.matcher(str);

        while (match.find()) {
            // Print matched Patterns
            System.out.println(match.group());
        }
    }
}
```

**Output**

```
GFG
gfg
```