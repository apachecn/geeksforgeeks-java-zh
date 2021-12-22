# Java 中的 Character.offsetByCodePoints()方法

> 原文:[https://www . geesforgeks . org/character-offsetbycodepoints-method-in-Java/](https://www.geeksforgeeks.org/character-offsetbycodepoints-method-in-java/)

**character . offset by codepoints(char sequence seq，int index，int codePointOffset)** 是 java 中的一个内置方法，它返回给定字符序列内的索引，该索引从给定索引偏移了 codePointOffset 代码点。由索引和代码点偏移量给定的文本范围内的不成对的替代项各计为一个代码点。

**语法:**

```
public static int offsetByCodePoints(CharSequence seq, int index, int codePointOffset)

```

**参数:**

*   *序列*–字符序列
*   *索引*–要偏移的索引
*   *代码点偏移量*–代码点的偏移量

**返回值:**字符类的这个方法返回字符序列内的索引。

**异常:**

*   NullPointerException–如果 seq 为空。
*   IndexOutOfBoundsException–如果索引为负或大于字符序列的长度，或者如果 codePointOffset 为正并且以索引开始的子序列的代码点少于 codePointOffset，或者如果 codePointOffset 为负并且索引之前的子序列的代码点少于 codePointOffset 的绝对值。

以下是说明上述方法的程序:
**程序 1:**

```
// Code to illustrate the offsetByCodePoints() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Create a CharSequence s and assign value
        CharSequence s = "Hello World";

        // Result of offsetByCodePoints on s
        String str = "The index within the char sequence s is " + 
        Character.offsetByCodePoints(s, 2, 6);

        // Print str value
        System.out.println(str);
    }
}
```

**Output:**

```
The index within the char sequence s is 8

```

**程序 2:**

```
// Code to illustrate the offsetByCodePoints() method

import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // Create a CharSequence s and assign value
        CharSequence s = "geeks for geeks";

        // Result of offsetByCodePoints on s
        String str = "The index within the char sequence s is " + 
        Character.offsetByCodePoints(s, 3, 8);

        // Print str value
        System.out.println(str);
    }
}
```

**Output:**

```
The index within the char sequence s is 11

```