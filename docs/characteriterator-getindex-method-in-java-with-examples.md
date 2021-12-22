# 用示例描述 Java 中的 getIndex()方法

> 原文:[https://www . geesforgeks . org/terminater-getindex-method-in-Java-with-examples/](https://www.geeksforgeeks.org/characteriterator-getindex-method-in-java-with-examples/)

**getIndex()** 法**法[法](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的特征化器接口**用来获取这个特征化器要读取的当前索引。此方法返回该索引号。

**语法:**

```
public int getIndex()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回将由该特征化器读取的索引号。

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

        System.out.println("Current Index: "
                           + characterIterator
                                 .getIndex());
    }
}
```

**输出:**

```
Current character: G
Current Index: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/terminater . html # getIndex–](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#getIndex--)