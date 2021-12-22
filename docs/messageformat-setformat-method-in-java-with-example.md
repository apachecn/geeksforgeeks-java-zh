# Java 中的 MessageFormat setFormat()方法，示例

> 原文:[https://www . geesforgeks . org/message format-set format-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-setformat-method-in-java-with-example/)

**java.text.MessageFormat** 类的 **setFormats()** 方法用于在该消息格式对象的模式中的特定索引处设置新的格式元素。

**语法:**

```
public void setFormat(int formatElementIndex,
                      Format newFormat)
```

**参数**:该方法将以下参数作为参数:

*   **Format Element Index:** This is the specific index where the new format element will be placed.
*   **New Format:** This is the new format element to be placed.

**返回值:**这个方法没有什么可返回的。

**异常:**如果 formatElementIndex 超出界限，此方法将引发**arrayindextofboundsexception**。

以下是说明**设置格式()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// setFormats() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, date, #}, {0, number, #.##}, {0, time}");

        // display the current pattern
        System.out.println("old pattern : "
                           + mf.toPattern());

        // getting all the format element
        // used in MessageFormat Object
        Format[] formats = mf.getFormats();

        // setting the new format element
        // at particular index
        // using setFormat() method
        for (int i = 0; i < formats.length; i++)
            mf.setFormat(i, formats[1]);

        // display the result
        System.out.println("\nnew pattern : "
                           + mf.toPattern());
    }
}
```

**输出:**

```
old pattern : {0,date, #}, {0,number, #0.##}, {0,time}

new pattern : {0,number, #0.##}, {0,number, #0.##}, {0,number, #0.##}

```

**例 2:**

```
// Java program to demonstrate
// setFormats() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing  MessageFormat
            MessageFormat mf
                = new MessageFormat("{0, date, #}, {0, number, #.##}, {0, time}");

            // display the current pattern
            System.out.println("old pattern : "
                               + mf.toPattern());

            // getting all the format element
            // used in MessageFormat Object
            Format[] formats = mf.getFormats();

            // setting the new format element
            // at particular index
            // using setFormat() method
            for (int i = 0; i <= formats.length + 1; i++)
                mf.setFormat(-1, formats[1]);

            // display the result
            System.out.println("\nnew pattern : "
                               + mf.toPattern());
        }
        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("\narray is out of bound");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
old pattern : {0,date, #}, {0,number, #0.##}, {0,time}

array is out of bound
Exception thrown : java.lang.ArrayIndexOutOfBoundsException: -1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # setFormat-int-Java . text . format-](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#setFormat-int-java.text.Format-)