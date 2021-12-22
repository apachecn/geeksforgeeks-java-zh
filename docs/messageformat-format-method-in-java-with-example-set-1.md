# Java 中的 MessageFormat format()方法，示例:Set–1

> 原文:[https://www . geesforgeks . org/message format-format-method-in-Java-with-example-set-1/](https://www.geeksforgeeks.org/messageformat-format-method-in-java-with-example-set-1/)

**java.text.MessageFormat** 类的 **format()** 方法用于获取追加到字符串缓冲区对象中的对象的格式化数组。格式化数组将包含位于 MessageFormat 对象模式中的所有形式的元素。

**语法:**

```
public final StringBuffer format(Object[] arguments,
                                 StringBuffer result,
                                 FieldPosition pos)
```

**参数** :

*   **Parameter:** -This method takes the array object as the parameter to be formatted.
*   **Result:-** The stringbuffer area will be used to attach the formatted array.
*   **Position:-** The field position will be used for alignment purposes.

**返回值:**该方法返回字符串缓冲区，该缓冲区将附加格式化数组的结果。

**异常:**如果结果为空，该方法抛出**空指针异常**。

以下是说明**格式()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// format() method

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

            // Creating and initializing new FieldPosition Object
            FieldPosition fp
                = new FieldPosition(MessageFormat.Field.ARGUMENT);

            // Creating and initializing an array of type Double
            // to be formated
            Object[] objs = { new Double(9.5678) };

            // Creating and initializing StringBuffer for
            // appending the result
            StringBuffer stb = new StringBuffer(10);

            // Formating an array of object
            // using format() method
            stb = mf.format(objs, stb, fp);

            // display the result
            System.out.println("formated array : "
                               + stb.toString());
        }
        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
formated array : 10, 9.57, 9.568

```

**例 2:**

```
// Java program to demonstrate
// format() method

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

            // Creating and initializing new FieldPosition Object
            FieldPosition fp
                = new FieldPosition(MessageFormat.Field.ARGUMENT);

            // Creating and initializing an array of type Double
            // to be formated
            Object[] objs = { new Double(9.5678) };

            // Creating and initializing StringBuffer for
            // appending the result
            StringBuffer stb = new StringBuffer(10);

            // Formating an array of object
            // using format() method
            stb = mf.format(objs, null, fp);

            // display the result
            System.out.println("formated array : "
                               + stb.toString());
        }
        catch (NullPointerException e) {
            System.out.println("StringBuffer is null " + e);
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```
old pattern : {0, date, #}, {1, date, #}, {0, number}

String is Null
StringBuffer is null java.lang.NullPointerException
Exception thrown : java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # format-Java . lang . object:A-Java . lang . stringbuffer-Java . text . field position-](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#format-java.lang.Object:A-java.lang.StringBuffer-java.text.FieldPosition-)