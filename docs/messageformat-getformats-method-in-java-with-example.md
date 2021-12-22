# Java 中的 MessageFormat getFormats()方法，示例

> 原文:[https://www . geesforgeks . org/message format-get formats-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-getformats-method-in-java-with-example/)

**java.text.MessageFormat** 类的 **getFormats()** 方法用于获取消息格式对象的先前设置模式所使用的格式。

**语法:**

```java
public Format[] getFormats()
```

**参数**:该方法不把任何参数作为参数。

**返回值:**该方法返回消息格式对象中先前设置的模式所使用的格式。

以下是说明 **getFormats()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getFormats() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, date, #}, {0, number, #.##}, {0, time}");

        // display the result
        System.out.println("pattern : "
                           + mf.toPattern());

        // getting all format
        // used in MessageFormat Object
        // using getFormats() method
        Format[] formats = mf.getFormats();

        // display the result
        System.out.println("\nRequired Formats are : ");
        for (int i = 0; i < formats.length; i++)
            System.out.println(formats[i]);
    }
}
```

**输出:**

```java
pattern : {0, date, #}, {0, number, #0.##}, {0, time}

Required Formats are : 
java.text.SimpleDateFormat@23
java.text.DecimalFormat@674dc
java.text.SimpleDateFormat@8400729

```

**例 2:**

```java
// Java program to demonstrate
// getFormats() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{1, number, integer}");

        // display the result
        System.out.println("pattern : "
                           + mf.toPattern());

        // getting all format
        // used in MessageFormat Object
        // using getFormats() method
        Format[] formats = mf.getFormats();

        // display the result
        System.out.println("\nRequired Formats are : ");
        for (int i = 0; i < formats.length; i++)
            System.out.println(formats[i]);
    }
}
```

**输出:**

```java
pattern : {1, number, integer}

Required Formats are : 
java.text.DecimalFormat@674dc

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # getFormats–](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#getFormats--)