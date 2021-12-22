# 用示例描述 Java 中的最后一个()方法

> 原文:[https://www . geesforgeks . org/terminater-last-method-in-Java-with-examples/](https://www.geeksforgeeks.org/characteriterator-last-method-in-java-with-examples/)

**最后()**法**法[法](https://www.geeksforgeeks.org/tag/java-text-package/)。[刻画符界面](https://www.geeksforgeeks.org/tag/java-characteriterator/)Java 中的**用来获取这个刻画符结尾的字符。此方法使用 getEndIndex()将迭代器的位置设置为最后一个字符，然后返回该字符。

**语法:**

```
public char last()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法使用 getEndIndex()，将迭代器的位置设置为最后一个字符，然后返回那个**字符**。

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

        System.out.println("Current character: "
                           + characterIterator
                                 .current());

        System.out.println("Last character: "
                           + characterIterator
                                 .last());
    }
}
```

**输出:**

```
Current character: G
Last character: s

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/terminater . html # last–](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#last--)