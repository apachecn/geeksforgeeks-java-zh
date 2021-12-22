# Java 中的 MessageFormat applyPattern()方法，示例

> 原文:[https://www . geesforgeks . org/message format-apply pattern-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-applypattern-method-in-java-with-example/)

**java.text.MessageFormat** 类的 **applyPattern()** 方法用于通过覆盖当前的 FormatElement、FormatType 和 FormatStyle 为当前的 MessageFormat 设置新的模式文本。

**语法:**

```
public void applyPattern(String newPattern)
```

**参数**:该方法以字符串**新模式**为参数，该参数是该消息格式对象的新文本模式。

**返回值:**此方法不返回任何内容。

**异常:**如果指定的新模式为空，该方法抛出**空指针异常**。

以下是说明**应用模式()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// applyPattern() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {0, number, #.##}, {0, number}");

        // display the result
        System.out.println("old pattern : "
                           + mf.toPattern());

        // applying new string pattern
        // to this MessageFormat Object
        // using applyPattern() method
        mf.applyPattern("{0, time, #}");

        // display the result
        System.out.println("\nnew pattern : "
                           + mf.toPattern());
    }
}
```

**输出:**

```
old pattern : {0, number, #}, {0, number, #0.##}, {0, number}

new pattern : {0, date, #}

```

**例 2:**

```
// Java program to demonstrate
// applyPattern() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing MessageFormat
            MessageFormat mf
                = new MessageFormat("{0, date, #}, {1, time, #}, {0, number}");

            // display the result
            System.out.println("old pattern : "
                               + mf.toPattern());

            // applying new string pattern
            // to this MessageFormat Object
            // using applyPattern() method
            mf.applyPattern(null);

            // display the result
            System.out.println("\nnew pattern : "
                               + mf.toPattern());
        }
        catch (NullPointerException e) {
            System.out.println("\nString is Null");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
old pattern : {0, date, #}, {1, date, #}, {0, number}

String is Null
Exception thrown : java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # apply pattern-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#applyPattern-java.lang.String-)