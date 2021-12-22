# Java 中 BreakIterator setText(字符串)方法，示例

> 原文:[https://www . geeksforgeeks . org/breakiterator-setextstring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-settextstring-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **setText()** 方法用于将新文本设置到 BreakIterator 中。
**语法:**

```
public void setText(String newText)
```

**参数**:该方法以字符串形式的**文本**为参数。
**返回值:**此方法不返回任何内容。
以下是举例说明 **setText()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate setText() method

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
        // using setText() method
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
// Java program to demonstrate setText() method

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
        // using setText() method
        wb.setText("GeeksForGeeks");

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
Retrieved text is : GeeksForGeeks
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # first–](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#first--)