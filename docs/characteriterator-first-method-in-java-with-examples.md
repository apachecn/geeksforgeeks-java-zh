# 用示例描述 Java 中的畸胎优先()方法

> 原文:[https://www . geesforgeks . org/terminater-first-in-Java-method-with-examples/](https://www.geeksforgeeks.org/characteriterator-first-method-in-java-with-examples/)

**先()**法 **[法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的特性描述符接口**用来获取这个特性描述符开头的字符。此方法使用 getBeginIndex()将迭代器的位置设置为第一个字符，然后返回该字符。

**语法:**

```
public char first()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法使用 getBeginIndex()，将迭代器的位置设置为第一个字符，然后返回该字符。

**异常:**这个方法不抛出任何异常。

**程序:**

```
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class CharacterIteratorDemo {
    public static void main(String[] args)
    {

        CharacterIterator characterIterator
            = new StringCharacterIterator(
                "GeeksForGeeks");

        System.out.println("First character: "
                           + characterIterator
                                 .first());
    }
}
```

**输出:**

```
First character: G

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/terminater . html # first–](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#first--)