# 用示例描述 Java 中的 getEndIndex()方法

> 原文:[https://www . geesforgeks . org/terminater-getendindex-method-in-Java-with-examples/](https://www.geeksforgeeks.org/characteriterator-getendindex-method-in-java-with-examples/)

**getEndIndex()**的**法的[法。Java 中的特征化器接口](https://www.geeksforgeeks.org/tag/java-text-package/)**用来获取这个特征化器要读取的结尾的索引。此方法返回该索引号。

**语法:**

```
public int getEndIndex()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回由该特征化器读取的结尾的**索引**号。

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

        System.out.println("Current EndIndex: "
                           + characterIterator
                                 .getEndIndex());
    }
}
```

**输出:**

```
Current EndIndex: 13

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/表征器. html # getEndIndex–](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#getEndIndex--)