# Java 中的 Character.valueOf()示例

> 原文:[https://www . geesforgeks . org/character-value of-in-Java-with-examples/](https://www.geeksforgeeks.org/character-valueof-in-java-with-examples/)

**Java . lang . Character . valueof()**是 Java 中的一个内置方法，它返回一个表示指定字符值的 Character 实例。如果不需要新的字符实例，通常会优先使用该方法而不是构造函数字符(char)，因为该方法通过缓存频繁请求的值可能会产生显著更好的空间和时间性能。此方法将始终缓存范围 **['\u0000 '到' \u007F']** 的值，并可能缓存此范围之外的其他值。

**语法:**

```
public static Character valueOf(char ch)

Parameter: 
ch- this parameter specifies the character.

```

**返回:**这个方法返回一个代表 ch 的字符实例。

下面的程序演示了 Java.lang.Character.valueOf()函数:

**程序 1:**

```
// Java program to demonstrate the
// Java.lang.Character.valueOf() method
// when the assigned char is a character

import java.lang.*;

public class Gfg {

    public static void main(String[] args)
    {
        // Create a character object
        Character c = new Character('z');

        // assign the primitive value to a character
        char ch = c.charValue();

        System.out.println("Character value of " + ch + " is " + c);
    }
}
```

**Output:**

```
Character value of z is z

```

**程序 2:**

```
// Java program to demonstrate the
// Java.lang.Character.valueOf() method
// when the assigned char is a number

import java.lang.*;

public class Gfg {

    public static void main(String[] args)
    {
        // Create a character object
        Character c = new Character('5');

        // assign the primitive value to a character
        char ch = c.charValue();

        System.out.println("Character value of " + ch + " is " + c);
    }
}
```

**Output:**

```
Character value of 5 is 5

```