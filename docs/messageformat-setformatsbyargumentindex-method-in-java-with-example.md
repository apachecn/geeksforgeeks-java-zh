# Java 中的 MessageFormat setFormatsByArgumentIndex()方法，示例

> 原文:[https://www . geesforgeks . org/message format-setformatsbyyargumentindex-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-setformatsbyargumentindex-method-in-java-with-example/)

**java.text.MessageFormat** 类的**setFormatsByArgumentIndex**方法用于通过覆盖旧模式来设置消息格式对象模式中新格式元素的数组。

**语法:**

```
public void setFormatsByArgumentIndex(Format[] newFormats)
```

**参数**:该方法以格式元素的**数组为参数，覆盖消息格式对象的旧模式。**

**返回值:**这个方法没有什么可返回的。

**异常:**如果新格式元素数组为空，该方法抛出**空指针异常**。

以下是说明**setFormatsByArgumentIndex()**方法的示例:

**例 1:**

```
// Java program to demonstrate
// setFormatsByArgumentIndex() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing  MessageFormat
            MessageFormat mf
                = new MessageFormat("{0, date, #}, {2, number, #.##}, {4, time}");

            // display the current message format object
            displayFormat(mf);

            // creating and initializing new Format object array
            Format[] format = { new SimpleDateFormat("YYYY-'W'ww-u"),
                                new DecimalFormat("10.5678") };

            // settting the new array of formats
            // in the pattern of MessageFormat object
            // using setFormatsByArgumentIndex() method
            mf.setFormatsByArgumentIndex(format);

            // display the Override MessageFormat object
            System.out.println();
            displayFormat(mf);
        }
        catch (NullPointerException e) {
            System.out.println("format array is null");
            System.out.println("Exception thrown : " + e);
        }
    }

    // Defining displayFormat method
    public static void displayFormat(MessageFormat mf)
    {

        // display the result
        System.out.println("pattern : "
                           + mf.toPattern());

        // getting all format
        // used in MessageFormat Object
        // using getFormats() method
        Format[] formats = mf.getFormats();

        // display the result
        System.out.println("Required Formats are : ");
        for (int i = 0; i < formats.length; i++)
            System.out.println(formats[i]);
    }
}
```

**输出:**

```
pattern : {0, date, #}, {2, number, #0.##}, {4, time}
Required Formats are : 
java.text.SimpleDateFormat@403
java.text.DecimalFormat@674fc
java.text.SimpleDateFormat@8400729

pattern : {0, date, YYYY-'W'ww-u}, {2, number, #0.##}, {4, time}
Required Formats are : 
java.text.SimpleDateFormat@d21287d2
java.text.DecimalFormat@674fc
java.text.SimpleDateFormat@8400729

```

**例 2:**

```
// Java program to demonstrate
// setFormatsByArgumentIndex() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing  MessageFormat
            MessageFormat mf
                = new MessageFormat("{0, date, #}, {2, number, #.##}, {4, time}");

            // display the current message format object
            displayFormat(mf);

            // creating and initializing new Format object array
            Format[] format = { new SimpleDateFormat("YYYY-'W'ww-u"),
                                new DecimalFormat("10.5678") };

            // settting the new array of formats
            // in the pattern of MessageFormat object
            // using setFormatsByArgumentIndex() method
            mf.setFormatsByArgumentIndex(null);

            // display the Override MessageFormat object
            System.out.println();
            displayFormat(mf);
        }
        catch (NullPointerException e) {
            System.out.println("\nformat array is null");
            System.out.println("Exception thrown : " + e);
        }
    }

    // Defining displayFormat method
    public static void displayFormat(MessageFormat mf)
    {

        // display the result
        System.out.println("pattern : "
                           + mf.toPattern());

        // getting all format
        // used in MessageFormat Object
        // using getFormats() method
        Format[] formats = mf.getFormats();

        // display the result
        System.out.println("Required Formats are : ");
        for (int i = 0; i < formats.length; i++)
            System.out.println(formats[i]);
    }
}
```

**输出:**

```
pattern : {0, date, #}, {2, number, #0.##}, {4, time}
Required Formats are : 
java.text.SimpleDateFormat@403
java.text.DecimalFormat@674fc
java.text.SimpleDateFormat@8400729

format array is null
Exception thrown : java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # setFormatsByArgumentIndex-Java . text . format:A-](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#setFormatsByArgumentIndex-java.text.Format:A-)