# 用示例描述 Java 中的畸胎克隆()方法

> 原文:[https://www . geesforgeks . org/terminater-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/characteriterator-clone-method-in-java-with-examples/)

**克隆()**法的 **[法的](https://www.geeksforgeeks.org/tag/java-text-package/)。Java 中的特性描述符接口**用来克隆这个特性描述符。这意味着此方法将创建另一个具有与此特性生成器相同的所有属性的特性生成器实例，并返回它。

**语法:**

```java
public Object clone()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**对象**，它是这个特征化器的克隆。

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

        String text = "GeeksForGeeks";

        CharacterIterator characterIterator
            = new StringCharacterIterator(text);

        System.out.println("Current CharacterIterator: "
                           + characterIterator);

        System.out.println("Cloned CharacterIterator: "
                           + characterIterator.clone());
    }
}
```

**输出:**

```java
Current CharacterIterator: java.text.StringCharacterIterator@c11e1b98
Cloned CharacterIterator: java.text.StringCharacterIterator@c11e1b98

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/terminater . html # clone–](https://docs.oracle.com/javase/9/docs/api/java/text/CharacterIterator.html#clone--)