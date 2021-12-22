# Java 中的 Character.isSpaceChar()方法

> 原文:[https://www . geesforgeks . org/character-isspacecharchar-ch-method-Java/](https://www.geeksforgeeks.org/character-isspacecharchar-ch-method-java/)

**java . lang . character . IsSpaceChar(char ch)**是 Java 中的一个内置方法，用于确定指定的字符是否是 Unicode 空格字符。当且仅当 Unicode 标准将字符指定为空格字符时，该字符才被视为空格字符。

如果角色的一般类别类型是下列任何一种，则此方法返回 true？

*   Space _ separator
*   Line _ separator
*   Paragraph _ separator

**语法:**

```java
public static boolean isSpaceChar(char ch)

```

**参数:**该函数接受一个强制参数 *ch* ，该参数指定要测试的字符。

**返回值:**这个方法返回一个布尔值。如果字符是空格字符，该值为*真*，否则为*假*。

下面的程序说明了 **Character.isSpaceChar()** 方法:

**程序 1:**

```java
// Java program to illustrate the
// Character.isSpaceChar() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 char primitives c1, c2 and assign values
        char c1 = '{content}apos;, c2 = '\u2025';

        // Function to check if the character is a unicode space or not
        boolean bool1 = Character.isSpaceChar(c1);
        System.out.println("c1 is a space character? " + bool1);

        // Function to check if the character is a unicode space or not
        boolean bool2 = Character.isSpaceChar(c2);
        System.out.println("c2 is a space character? " + bool2);
    }
}
```

**输出:**

```java
c1 is a space character? false
c2 is a space character? false

```

**程序二:**

```java
// Java program to illustrate the
// Character.isSpaceChar() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 char primitives
        // c1, c2 and assign values
        char c1 = '*', c2 = '\u2028';

        // Function to check if the character is a unicode space or not
        boolean bool1 = Character.isSpaceChar(c1);
        System.out.println("c1 is a space character? " + bool1);

        // Function to check if the character is a unicode space or not
        boolean bool2 = Character.isSpaceChar(c2);
        System.out.println("c2 is a space character? " + bool2);
    }
}
```

**输出:**

```java
c1 is a space character? false
c2 is a space character? true

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # isSpaceChar(char)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isSpaceChar(char))