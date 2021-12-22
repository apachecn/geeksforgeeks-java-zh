# Java 中的 Character.isMirrored()，示例

> 原文:[https://www . geesforgeks . org/character-is mirrored-in-Java-with-examples/](https://www.geeksforgeeks.org/character-ismirrored-in-java-with-examples/)

**java . lang . character . Ismirrored()**是 Java 中的一个内置方法，用于确定字符是否根据 Unicode 规范进行镜像。当在从右向左的文本中显示时，镜像字符的字形应该水平镜像。例如，' \u0028 '左括号在语义上被定义为左括号。这将在从左到右的文本中显示为“(”但在从右到左的文本中显示为“)”。镜像角色的例子有 **[ ] { } ( )** 等。

**语法:**

```
public static boolean isMirrored(char ch)

Parameters: 
ch - char for which the mirrored property is requested

```

**返回:**如果字符被镜像，该方法返回真，否则如果字符未被镜像或未定义，该方法返回假。

下面是 Character.isMirrored()方法的示例:

**程序 1:**

```
// Java program to demonstrate the
// Character.isMirrored() function
// When the character is a valid one.
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Assign values to ch1, ch2, ch3, ch4
        char ch1 = '[';
        char ch2 = '+';
        char ch3 = '}';
        char ch4 = '(';

        // Checks if the character is mirrored or not and prints
        boolean b1 = Character.isMirrored(ch1);
        System.out.println(ch1 + " is a mirrored character is " + b1);

        boolean b2 = Character.isMirrored(ch2);
        System.out.println(ch2 + " is a mirrored character is " + b2);

        boolean b3 = Character.isMirrored(ch1);
        System.out.println(ch3 + " is a mirrored character is " + b3);

        boolean b4 = Character.isMirrored(ch2);
        System.out.println(ch4 + " is a mirrored character is " + b4);
    }
}
```

**Output:**

```
[ is a mirrored character is true
+ is a mirrored character is false
} is a mirrored character is true
( is a mirrored character is false

```

**程序 2:**

```
// Java program to demonstrate the
// Character.isMirrored() function
// When the character is a invalid one.
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Assign values to ch1, ch2, ch3, ch4
        char ch1 = '4';
        char ch2 = '0';

        // Checks if the character is mirrored or not and prints
        boolean b1 = Character.isMirrored(ch1);
        System.out.println(ch1 + " is a mirrored character is " + b1);

        boolean b2 = Character.isMirrored(ch2);
        System.out.println(ch2 + " is a mirrored character is " + b2);
    }
}
```

**Output:**

```
4 is a mirrored character is false
0 is a mirrored character is false

```