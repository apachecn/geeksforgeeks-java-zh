# Java 中 Character.isWhitespace()方法，带示例

> 原文:[https://www . geesforgeks . org/character-ishitespace-method-in-Java-with-examples/](https://www.geeksforgeeks.org/character-iswhitespace-method-in-java-with-examples/)

**java . lang . character . ishitespace()**是 java 中的一个内置方法，根据 Java 判断指定的字符(Unicode 代码点)是否为空格。当且仅当字符满足以下条件之一时，它才是 Java 空白字符:

*   它是一个 Unicode 空格字符(SPACE_SEPARATOR、LINE_SEPARATOR 或 PARATION _ SEPARATOR)，但也不是非中断空格(' \u00A0 '、' \u2007 '、' \u202F ')。
*   它是' \t '，U+0009 水平列表。
*   它是' \n '，U+000A 线路馈电。
*   它是' \u000B '，U+000B 垂直制表。
*   它是“\f”，U+000C FORM FEED。
*   它是' \r '，U+000D 回车。
*   是' \u001C '，U+001C 文件分隔符。
*   它是' \u001D '，U+001D 组分隔符。
*   它是' \u001E '，U+001E 记录分隔符。
*   它是“\u001F”，U+001F 单位分隔符。

**语法:**

```
public static boolean isWhitespace(datatype character)

```

**参数**:该功能接受一个强制参数**字符**。该参数可以是数据类型 int 或 char。它指定要测试的字符。

**返回值:**如果字符是 Java 空白字符，则该方法返回 true，否则返回 false。

下面的程序说明了字符空间方法:

**程序 1:**

```
// Java program to illustrate the Character.isWhitespace()
// method when the passed parameter is a character
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 char primitives c1, c2
        char c1 = '*', c2 = '\f';

        boolean b1 = Character.isWhitespace(c1);
        boolean b2 = Character.isWhitespace(c2);

        String str1 = "c1 is a Java whitespace character is " + b1;
        String str2 = "c2 is a Java whitespace character is " + b2;

        // print b1, b2 values
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**输出**:

```
c1 is a Java whitespace character is false
c2 is a Java whitespace character is true

```

**程序 2:**

```
// Java program to demonstrate the Character.isWhitespace()
// method when the passed parameter is a character
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 char primitives c1, c2
        char c1 = '/', c2 = '\f';

        boolean b1 = Character.isWhitespace(c1);
        boolean b2 = Character.isWhitespace(c2);

        String str1 = "c1 is a Java whitespace character is " + b1;
        String str2 = "c2 is a Java whitespace character is " + b2;

        // print b1, b2 values
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**输出**:

```
c1 is a Java whitespace character is false
c2 is a Java whitespace character is true

```

**程序 3:** 当参数类型为 *int* 时。

```
// Java program to demonstrate the
// Character.isWhitespace()
// method when the passed parameter
// is a character
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 int primitives c1, c2
        int c1 = 0x451c, c2 = 0x4abc;

        boolean b1 = Character.isWhitespace(c1);
        boolean b2 = Character.isWhitespace(c2);

        String str1 = "c1 represents Java whitespace character is " + b1;
        String str2 = "c2 represents Java whitespace character is " + b2;

        // print b1, b2 values
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**输出**:

```
c1 represents Java whitespace character is false
c2 represents Java whitespace character is false

```

**程序 4:** 当参数类型为 *int* 时。

```
// Java program to demonstrate the Character.isWhitespace()
// method when the passed parameter is a character
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 int primitives c1, c2
        int c1 = 0x001c, c2 = 0x1bbc;

        boolean b1 = Character.isWhitespace(c1);
        boolean b2 = Character.isWhitespace(c2);

        String str1 = "c1 represents Java whitespace character is " + b1;
        String str2 = "c2 represents Java whitespace character is " + b2;

        // print b1, b2 values
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**输出**:

```
c1 represents Java whitespace character is true
c2 represents Java whitespace character is false

```