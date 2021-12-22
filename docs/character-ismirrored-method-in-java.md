# Java 中 Character.isMirrored()方法

> 原文:[https://www . geesforgeks . org/character-is mirrored-method-in-Java/](https://www.geeksforgeeks.org/character-ismirrored-method-in-java/)

**character . Ismirrored(int CodePoint)**是 java 中的一个内置方法，用于确定指定的字符(Unicode 代码点)是否根据 Unicode 规范进行了镜像。当在从右向左的文本中显示时，镜像字符的字形应该水平镜像。例如，' \u0028 '左括号在语义上被定义为左括号。这将在从左到右的文本中显示为“(”但在从右到左的文本中显示为“)”。

**语法:**

```java
public static boolean isMirrored(int codePoint)

```

**参数:**整数类型的参数*码点*是需要测试的字符(Unicode 码点)。

**返回值:**如果角色被镜像，该方法返回 true，如果角色未被镜像或未被定义，则返回 false。

下面的程序说明了 Character.isMirrored()方法:

**程序 1:**

```java
// Code to illustrate the isMirrored() method
import java.lang.*;
public class gfg {

    public static void main(String[] args)
    {

        // Creating 2 int primitives char1, char2
        int char1 = 0x0c05, char2 = 0x013c;

        // Checks if character is mirrored or not and prints
        boolean bool1 = Character.isMirrored(char1);
        String str1 = "char1 represents a mirrored character is " + bool1;
        System.out.println(str1);

        boolean bool2 = Character.isMirrored(char2);
        String str2 = "char2 represents a mirrored character is " + bool2;
        System.out.println(str2);
    }
}
```

**输出:**

```java
char1 represents a mirrored character is false
char2 represents a mirrored character is false

```

**程序二:**

```java
// Code to illustrate the isMirrored() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Create 2 int primitives c1, c2
        int c1 = 0x0c07, c2 = 0x063c;

        // Checks if character is mirrored or not and prints
        boolean bool1 = Character.isMirrored(c1);
        String str1 = "c1 represents a mirrored character is " + bool1;
        System.out.println(str1);

        boolean bool2 = Character.isMirrored(c2);
        String str2 = "c2 represents a mirrored character is " + bool2;
        System.out.println(str2);
    }
}
```

**输出:**

```java
c1 represents a mirrored character is false
c2 represents a mirrored character is false

```

参考:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # Ismirrored(int)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#isMirrored(int))