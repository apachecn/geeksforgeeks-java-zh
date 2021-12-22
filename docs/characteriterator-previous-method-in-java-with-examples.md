# 用示例描述 Java 中以前的方法

> 原文:[https://www . geesforgeks . org/terminater-previous-method-in-Java-with-examples/](https://www.geeksforgeeks.org/characteriterator-previous-method-in-java-with-examples/)

**前朝()**法 **[法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的特性描述符接口**用于获取该特性描述符要读取的前一个字符。这个方法将迭代器向后递减一个索引，并返回前一个字符。

**语法:**

```java
public char previous()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回将由该特性生成器读取的前一个字符。

**异常:**这个方法不抛出任何异常。

**程序:**

```java
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

        characterIterator.next();

        System.out.println("Current character: "
                           + characterIterator
                                 .current());

        System.out.println("Previous character: "
                           + characterIterator
                                 .previous());
    }
}
```

**输出:**

```java
Current character: e
Previous character: G

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/terminater . html # previous–](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#previous--)