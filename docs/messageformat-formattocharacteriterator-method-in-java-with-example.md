# Java 中的 MessageFormat format format to character()方法，示例

> 原文:[https://www . geeksforgeeks . org/messageformat-formattocharacteriator-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-formattocharacteriterator-method-in-java-with-example/)

**java.text.MessageFormat** 类的**format to character()**方法用于格式化对象数组，并将它们插入消息格式对象的模式中。

**语法:**

```java
public AttributedCharacterIterator formatToCharacterIterator(Object arguments)
```

**参数**:该方法将对象数组作为参数进行格式化。

**返回值:**这个方法返回属性字符迭代器，它将描述格式化的值。

**异常:**如果参数为空，该方法抛出**空指针异常**。

以下是举例说明**格式特征描述符()**方法的例子:

**例 1:**

```java
// Java program to demonstrate
// formatToCharacterIterator() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing new MessageFormat Object
            MessageFormat mf
                = new MessageFormat("{0, number, #}, {0, number, #.##}, {0, number}");

            // Creating and initializing an array of type Double
            // to be formated
            Object[] objs = { new Double(4.234567) };

            // Formating an array of object
            // using formatToCharacterIterator() method
            CharacterIterator str = mf.formatToCharacterIterator(objs);

            // display the result
            System.out.print("formatted array : ");
            System.out.print(str.first());
            for (int i = 0; i <= str.getEndIndex() - 2; i++)
                System.out.print(str.next());
        }
        catch (NullPointerException e) {
            System.out.println("pattern is null ");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
formatted array : 4, 4.23, 4.235

```

**例 2:**

```java
// Java program to demonstrate
// formatToCharacterIterator() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing new MessageFormat Object
            MessageFormat mf
                = new MessageFormat("{0, number, #}, {0, number, #.##}, {0, number}");

            // Creating and initializing an array of type Double
            // to be formated
            Object[] objs = { new Double(4.234567) };

            // Formating an array of object
            // using formatToCharacterIterator() method
            CharacterIterator str = mf.formatToCharacterIterator(null);

            // display the result
            System.out.print("formatted array : ");
            System.out.print(str.first());
            for (int i = 0; i <= str.getEndIndex() - 2; i++)
                System.out.print(str.next());
        }
        catch (NullPointerException e) {
            System.out.println("argument is null ");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
argument is null 
Exception thrown : java.lang.NullPointerException: formatToCharacterIterator must be passed non-null object

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # formattocharactersterator-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#formatToCharacterIterator-java.lang.Object-)