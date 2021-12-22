# Java 中的 character . issuplementarycode point()方法

> 原文:[https://www . geesforgeks . org/character-issuplementarycode point-method-in-Java/](https://www.geeksforgeeks.org/character-issupplementarycodepoint-method-in-java/)

**java . lang . character . issuplementAryCodePoint(int CodePoint)**是 Java 中的一个内置方法，用于确定指定的字符(Unicode 代码点)是否在补充字符范围内。

**语法:**

```
public static boolean isSupplementaryCodePoint(int codePoint)

```

**参数:**整数型的*码点*是指需要测试的字符(Unicode 码点)。

**返回值:**如果指定的码点在 MIN _ sublimited _ CODE _ POINT 和 MAX_CODE_POINT(含)之间，则该方法返回 true，否则返回 false。

下面的程序说明了 character . issuplementarycode point()方法:

**程序 1:**

```
// Code to illustrate the isSupplementaryCodePoint() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Create 2 int primitives c1, c2 and assign values
        int c1 = 0x10ffd, c2 = 0x154ca;

        boolean bool1 = Character.isSupplementaryCodePoint(c1);
        boolean bool2 = Character.isSupplementaryCodePoint(c2);

        String str1 = "c1 represents a supplementary code point is " + bool1;
        String str2 = "c2 represents a supplementary code point is " + bool2;

        // Displaying the result
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**输出:**

```
c1 represents a supplementary code point is true
c2 represents a supplementary code point is true

```

**程序二:**

```
// Code to illustrate the isSupplementaryCodePoint() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Creates 2 int primitives c1, c2 and assign values
        int c1 = 0x45ffd, c2 = 0x004ca;

        boolean bool1 = Character.isSupplementaryCodePoint(c1);
        boolean bool2 = Character.isSupplementaryCodePoint(c2);

        String str1 = "c1 represents a supplementary code point is " + bool1;
        String str2 = "c2 represents a supplementary code point is " + bool2;

        // Displaying the result
        System.out.println(str1);
        System.out.println(str2);
    }
}
```

**输出:**

```
c1 represents a supplementary code point is true
c2 represents a supplementary code point is false

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # issuplementarycode point(int)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isSupplementaryCodePoint(int))