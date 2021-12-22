# Java 中的 Character.isLetterOrDigit()，示例

> 原文:[https://www . geesforgeks . org/character-isletterordigit-in-Java-with-examples/](https://www.geeksforgeeks.org/character-isletterordigit-in-java-with-examples/)

**java . lang . character . IsletterOrdigit(char ch)**是 Java 中的一个内置方法，用于确定指定的字符是字母还是数字。

**语法:**

```java
public static boolean isLetterOrDigit(char ch)

```

**参数:**该函数接受单个强制参数 ***ch*** ，表示要测试的字符。

**返回值:**该函数返回一个布尔值。如果字符是字母或数字，布尔值为*真*，否则为*假*。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program to illustrate the
// Character.isLetterOrDigit() method

import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        // two characters
        char c1 = 'Z', c2 = '2';

        // Function to check if the character is letter or digit
        boolean bool1 = Character.isLetterOrDigit(c1);
        System.out.println(c1 + " is a letter/digit ? " + bool1);

        // Function to check if the character is letter or digit
        boolean bool2 = Character.isLetterOrDigit(c2);
        System.out.println(c2 + " is a letter/digit ? " + bool2);
    }
}
```

**输出:**

```java
Z is a letter/digit ? true
2 is a letter/digit ? true

```

**程序二:**

```java
// Java program to illustrate the
// Character.isLetterOrDigit() method

import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        // assign character
        char c1 = 'D', c2 = '/';

        // Function to check if the character is letter or digit
        boolean bool1 = Character.isLetterOrDigit(c1);
        System.out.println(c1 + " is a letter/digit ? " + bool1);

        // Function to check if the character is letter or digit
        boolean bool2 = Character.isLetterOrDigit(c2);
        System.out.println(c2 + " is a letter/digit ? " + bool2);
    }
}
```

**输出:**

```java
D is a letter/digit ? true
/ is a letter/digit ? false

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # isLetterOrDigit(char)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isLetterOrDigit(char))