# Java 中的 MessageFormat setFormats()方法，示例

> 原文:[https://www . geesforgeks . org/message format-set formats-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-setformats-method-in-java-with-example/)

**java.text.MessageFormat** 类的 **setFormats()** 方法是通过覆盖旧模式来设置消息格式对象的模式中新格式元素的数组。

**语法:**

```java
public void setFormats(Format[] newFormats)
```

**参数:**该方法以格式元素数组作为参数，用于覆盖消息格式对象的旧模式。
**返回值:**这个方法没有什么可返回的。
**异常:**如果新格式元素数组为空，该方法抛出**NullPointRexception**。

以下是说明**设置格式()**方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
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

            // display the current message format object
            displayFormat(mf);

            // creating and initializing new Format object array
            Format[] format = { new SimpleDateFormat("YYYY-'W'ww-u"),
                                new DecimalFormat("0.##") };

            // setting the new array of formats
            // in the pattern of MessageFormat object
            // using setFormats() method
            mf.setFormats(format);

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

**Output:** 

```java
pattern : {0, date, #}, {0, number, #0.##}, {0, time}
Required Formats are : 
java.text.SimpleDateFormat@403
java.text.DecimalFormat@674fc
java.text.SimpleDateFormat@8400729

pattern : {0, date, YYYY-'W'ww-u}, {0, number, #0.##}, {0, time}
Required Formats are : 
java.text.SimpleDateFormat@d21287d2
java.text.DecimalFormat@674dc
java.text.SimpleDateFormat@8400729
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
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

            // display the current message format object
            displayFormat(mf);

            // creating and initializing new Format object array
            Format[] format = { new SimpleDateFormat("YYYY-'W'ww-u"),
                                new DecimalFormat("0.##") };

            // setting the new array of formats
            // in the pattern of MessageFormat object
            // using setFormats() method
            mf.setFormats(null);

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

**Output:** 

```java
pattern : {0, date, #}, {0, number, #0.##}, {0, time}
Required Formats are : 
java.text.SimpleDateFormat@403
java.text.DecimalFormat@674fc
java.text.SimpleDateFormat@8400729

format array is null
Exception thrown : java.lang.NullPointerException
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # setFormats-Java . text . format:A-T4】