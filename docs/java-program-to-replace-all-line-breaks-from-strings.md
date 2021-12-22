# 替换字符串中所有换行符的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-replace-all-line-break-from-strings/](https://www.geeksforgeeks.org/java-program-to-replace-all-line-breaks-from-strings/)

给定一个字符串，编写一个 Java 程序来替换给定字符串中的所有换行符。

**示例**

```
Input - Geeks
        For
        Geeks

Output - Geeks For Geeks
```

**换行符:**换行符(" \n ")是定义换行符的单个字符。

为了替换字符串中的所有换行符，可以使用 replace()函数。

**String replace():** 此方法返回一个新的 String 对象，该对象包含与原始字符串相同的字符序列，但给定的字符被另一个给定的字符替换。

**语法:**

```
public String replace(char old,char new)
```

**参数:**

*   Old: Old Role
*   New: new role

**返回值:**用新字符

替换旧字符返回字符串

## Java

```
// Java Program to Replace All
// Line Breaks from Strings

public class remove {
    public static void main(String[] args)
    {
        String s = "Replace\n"
                   + " all\n"
                   + " line\n"
                   + " breaks\n"
                   + " from\n"
                   + " strings";

        System.out.println(
            "Original String with line breaks - " + s);

        // replacing line breaks from string
        s = s.replace("\n", "");

        System.out.println(
            "String after replacing line breaks - " + s);
    }
}
```

**输出**

```
Original String with line breaks - Replace
 all
 line
 breaks
 from
 strings
String after replacing line breaks - Replace all line breaks from strings
```