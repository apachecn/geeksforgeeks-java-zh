# 用示例描述 Java 中的 next()方法

> 原文:[https://www . geesforgeks . org/terminater-next-method-in-Java-with-examples/](https://www.geeksforgeeks.org/characteriterator-next-method-in-java-with-examples/)

**接下来()**法**法[法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的特性描述符接口**用于获取该特性描述符要读取的下一个字符。这个方法将迭代器向前递减一个索引，并返回下一个字符。

**语法:**

```java
public char next()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回下一个字符，这个字符将被这个特征化器读取。

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

        System.out.println("Current character: "
                           + characterIterator
                                 .current());

        System.out.println("Next character: "
                           + characterIterator
                                 .next());
    }
}
```

**输出:**

```java
Current character: G
Next character: e

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/terminater . html # next–](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#next--)