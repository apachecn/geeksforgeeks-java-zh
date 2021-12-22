# Java 中 character . isunicodeidentifier part()方法，带示例

> 原文:[https://www . geeksforgeeks . org/character-isunicodeidentifier part-method-in-Java-with-examples/](https://www.geeksforgeeks.org/character-isunicodeidentifierpart-method-in-java-with-examples/)

**java . lang . character . isunicodeidentifier part()**是 Java 中的一个内置方法，它确定指定的字符是否可能是 Unicode 标识符的一部分，而不是第一个字符。

当且仅当下列陈述之一为真时，字符可以是 Unicode 标识符的一部分:

*   它是一个连接标点符号(如“_”)
*   这是一个数字
*   这是一封信
*   这是一个组合标记
*   对于此字符，isIdentifierIgnorable 返回 true。
*   它是一个数字字母(如罗马数字字符)
*   这是一个无间距标记

**语法:**

```
public static boolean isUnicodeIdentifierPart(datatype character)

```

**参数:**该功能接受一个强制参数*字符*。该参数可以是数据类型 int 或 char。它指定要测试的字符。

**返回值:**如果字符可能是 Unicode 标识符的一部分，则该方法返回 true，否则返回 false。

下面的程序说明了 Java . lang . Character . isunicodeidentifier part()方法:
**程序 1:** 当传递的参数是一个字符时。

```
// Code to illustrate the Character.isUnicodeIdentifierPart() 
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Creating character primitives
        char char1 = '-';
        char char2 = '7';
        char char3 = 'g';

        boolean bool1 = Character.isUnicodeIdentifierPart(char1);
        boolean bool2 = Character.isUnicodeIdentifierPart(char2);
        boolean bool3 = Character.isUnicodeIdentifierPart(char3);

        String str1 = " Is " + char1 + " a part of Unicode Identifier: " + bool1;
        String str2 = " Is " + char2 + " a part of Unicode Identifier: " + bool2;
        String str3 = " Is " + char3 + " a part of Unicode Identifier: " + bool3;

                // Displaying the strings
        System.out.println(str1);
        System.out.println(str2);
        System.out.println(str3);
    }
}
```

**Output:**

```
Is - a part of Unicode Identifier: false
 Is 7 a part of Unicode Identifier: true
 Is g a part of Unicode Identifier: true

```

**程序 2:** 当传递的参数是字符时。

```
// Code to illustrate the Character.isUnicodeIdentifierPart() 
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Create 2 char primitives c1, c2
        char c1 = '~', c2 = '8';

        boolean bool1 = Character.isUnicodeIdentifierPart(c1);
        boolean bool2 = Character.isUnicodeIdentifierPart(c2);

        String str1 = c1 + " may be part of a Unicode identifier is " + bool1;
        String str2 = c2 + " may be part of a Unicode identifier is " + bool2;

        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**Output:**

```
~ may be part of a Unicode identifier is false
8 may be part of a Unicode identifier is true

```

下面的程序说明了字符识别部分方法:

**程序 1:**

```
// Code to illustrate the Character.isUnicodeIdentifierPart(int codePoint)
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Create 2 int primitives c1, c2
        int c1 = 0x053d, c2 = 0x7840;

        boolean bool1 = Character.isUnicodeIdentifierPart(c1);
        boolean bool2 = Character.isUnicodeIdentifierPart(c2);

        String str1 = "c1 may be part of a Unicode identifier is " + bool1;
        String str2 = "c2 may be part of a Unicode identifier is " + bool2;

        // Displaying the strings
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**Output:**

```
c1 may be part of a Unicode identifier is true
c2 may be part of a Unicode identifier is true

```

**程序 2:**

```
// Code to illustrate the Character.isUnicodeIdentifierPart(int codePoint)
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Creating 2 int primitives c1, c2
        int c1 = 0x065d, c2 = 0x7885;

        boolean bool1 = Character.isUnicodeIdentifierPart(c1);
        boolean bool2 = Character.isUnicodeIdentifierPart(c2);

        String str1 = "c1 may be part of a Unicode identifier is " + bool1;
        String str2 = "c2 may be part of a Unicode identifier is " + bool2;

        // Displaying the strings
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**Output:**

```
c1 may be part of a Unicode identifier is true
c2 may be part of a Unicode identifier is true

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # isunicodeidentifier part(char)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isUnicodeIdentifierPart(char))