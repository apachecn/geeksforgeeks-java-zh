# 用示例描述 Java 中的 TerterSetIndex()方法

> 原文:[https://www . geesforgeks . org/terminater-set index-method-in-Java-with-examples/](https://www.geeksforgeeks.org/characteriterator-setindex-method-in-java-with-examples/)

**[的**设置索引()**方法。Java 中的特征化器接口](https://www.geeksforgeeks.org/tag/java-text-package/)**用来设置这个特征化器要读取的当前索引。此方法将待设置的索引作为参数，并在该索引处设置此字符的索引，然后返回该字符。

**语法:**

```java
public char setIndex(int index)

```

**参数:**该方法以待设置的索引为参数，设置该表征器的索引。

**返回值:**该方法返回该方法设置的索引处的字符。

**异常:**如果指定的索引不在有效范围(getBeginIndex()、getEndIndex()–1)内，此方法将引发 IllegalArgumentException。

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

        System.out.println("Current Index: "
                           + characterIterator
                                 .getIndex());

        int index = 5;

        System.out.println("Updated the index to : "
                           + index);

        System.out.println("Character at new"
                           + " current index: "
                           + characterIterator
                                 .setIndex(index));
    }
}
```

**输出:**

```java
Current Index: 0
Updated the index to : 5
Character at new current index: F

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/terminater . html # setIndex-int-](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#setIndex-int-)