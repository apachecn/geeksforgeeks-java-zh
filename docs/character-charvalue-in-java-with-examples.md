# Java 中的 Character.charValue()，示例

> 原文:[https://www . geeksforgeeks . org/char-char value-in-Java-with-examples/](https://www.geeksforgeeks.org/character-charvalue-in-java-with-examples/)

**Java . lang . character . charvalue()**是 Java 中的内置方法，返回这个字符对象的值。此方法将字符对象转换为其基本数据类型字符。

**语法:**

```java
public char charValue() 

The function does not accepts any parameter. 

```

**返回类型:**这个方法返回这个对象所表示的原始字符值。

下面的程序说明了 Java.lang.Character.charValue()方法:

**程序 1:**

```java
// Java program to demonstrate the
// Java.lang.Character.charValue() method
// when the assigned char is a character

import java.lang.*;

public class Gfg1 {

    public static void main(String[] args)
    {
        // Create a character object
        Character x = new Character('z');

        // assign the primitive value to a character
        char ch = x.charValue();

        System.out.println("Primitive char value is " + ch);
    }
}
```

**Output:**

```java
Primitive char value is z

```

**程序 2:** 当我们给 x 的值赋任意数字时:

```java
// Java program to demonstrate the
// function when the assigned value is
// a number
import java.lang.*;

public class Gfg {

    public static void main(String[] args)
    {
        // create a Character object x
        Character x = new Character('9');

        // assign value is a number
        // assign the primitive value to a character
        char ch = x.charValue();

        // print the primitive char value
        System.out.println("Primitive char value is " + ch);
    }
}
```

**Output:**

```java
Primitive char value is 9

```