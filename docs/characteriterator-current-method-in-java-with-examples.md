# 用示例描述 Java 中的畸胎电流()方法

> 原文:[https://www . geesforgeks . org/terminater-current-method-in-Java-with-examples/](https://www.geeksforgeeks.org/characteriterator-current-method-in-java-with-examples/)

**电流()**方法**T3。Java 中的特性描述符接口**用来获取当前要被这个特性描述符读取的字符。此方法返回当前字符。

**语法:**

```
public char current()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回当前字符，该字符将由该字符生成器读取。

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
    }
}
```

**输出:**

```
Current character: G

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/terminater . html # current–](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#current--)