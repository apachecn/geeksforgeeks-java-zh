# Java 中的 BreakIterator getText()方法，带示例

> 原文:[https://www . geesforgeks . org/breakiterator-gettext-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-gettext-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **getText()** 方法用于获取 BreakIterator 中 setText()方法预先设置的文本。
**语法:**

```
public abstract CharacterIterator getText()
```

**参数:**此方法不接受任何参数。
**返回值:**此方法提供之前扫描的文本。
以下是举例说明 **getText()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate getText() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        wb.setText("Code Geeks");

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

```
Retrieved text is : Code Geeks
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate getText() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        wb.setText("Geeks For GEeks");

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

```
Retrieved text is : Geeks For GEeks
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # getText–T4】