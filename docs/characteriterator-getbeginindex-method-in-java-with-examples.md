# 用示例描述 Java 中的 getBeginIndex()方法

> 原文:[https://www . geesforgeks . org/terminater-getbeginindex-method-in-Java-with-examples/](https://www.geeksforgeeks.org/characteriterator-getbeginindex-method-in-java-with-examples/)

**getBeginIndex()** 法的**法的[法的](https://www.geeksforgeeks.org/tag/java-text-package/)法。Java 中的[terminater 接口](https://www.geeksforgeeks.org/tag/java-characteriterator/)** 用来获取这个 terminater 要读取的开头的索引。此方法返回该索引号。

**语法:**

```java
public int getBeginIndex()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回由该特征化器读取的开头的**索引号**。

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

        System.out.println("BeginIndex: "
                           + characterIterator
                                 .getBeginIndex());
    }
}
```

**输出:**

```java
BeginIndex: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/表征器. html # getBeginIndex–](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#getBeginIndex--)