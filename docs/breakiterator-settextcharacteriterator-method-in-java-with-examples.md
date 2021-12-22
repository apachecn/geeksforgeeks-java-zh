# Java 中 BreakIterator setText(特性生成器)方法，示例

> 原文:[https://www . geeksforgeeks . org/breakiterator-setextternatureterator-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-settextcharacteriterator-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **setText(特性迭代器)**方法用于使用特性迭代器对象将新文本设置到 BreakIterator 中。

**语法:**

```java
public abstract void setText(CharacterIterator newText)
```

**参数:**该方法以**特征描述符**对象为参数，该参数包含要设置的新文本。

**返回值:**此方法不返回任何内容。

以下是说明**设置文本()**方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate setText() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing CharacterIterator object
        CharacterIterator word
            = new StringCharacterIterator("GeeksForGEEks");

        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        // using setText() method
        wb.setText(word);

        // getting the text being scanned by
        // using getText() method
        StringCharacterIterator text
            = (StringCharacterIterator)wb.getText();

        // display the result
        System.out.print("Retrieved text is : "
                         + text.first());
        for (int i = text.getBeginIndex() - 1;
             i < text.getEndIndex() - 2;
             i++)
            System.out.print(text.next());
    }
}
```

**Output**

```java
Retrieved text is : GeeksForGEEks
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate setText() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing CharacterIterator object
        CharacterIterator word
            = new StringCharacterIterator("TextView");

        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        // using setText() method
        wb.setText(word);

        // getting the text being scanned by
        // using getText() method
        StringCharacterIterator text
            = (StringCharacterIterator)wb.getText();

        // display the result
        System.out.print("Retrieved text is : "
                         + text.first());
        for (int i = text.getBeginIndex() - 1;
             i < text.getEndIndex() - 2;
             i++)
            System.out.print(text.next());
    }
}
```

**Output**

```java
Retrieved text is : TextView
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # setText-Java . text .表征器-](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#setText-java.text.CharacterIterator-)