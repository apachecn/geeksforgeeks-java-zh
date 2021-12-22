# Java 中的 MessageFormat getFormatsByArgumentIndex()方法，示例

> 原文:[https://www . geesforgeks . org/message format-getformatsbyyargumentindex-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-getformatsbyargumentindex-method-in-java-with-example/)

**java.text.MessageFormat** 类的 **getFormats()** 方法用于按时间顺序获取消息格式对象模式中存在的每个参数索引的格式。如果特定参数索引没有格式，它将返回 null。
**语法:**

```java
public Format[] getFormatsByArgumentIndex()
```

**参数**:该方法不把任何参数作为参数。
**返回值:**该方法按时间顺序返回消息格式对象模式中存在的每个参数索引的格式。
以下是举例说明**getFormatsByArgumentIndex()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            = new MessageFormat("{1, number, integer}, {2, number, float}, {5, date}");

        // display the result
        System.out.println("pattern : "
                           + mf.toPattern());

        // getting all the format
        // used in MessageFormat Object
        // using getFormatsByArgumentIndex() method
        Format[] formats = mf.getFormatsByArgumentIndex();

        // display the result
        System.out.println("\nRequired Formats are : ");
        for (int i = 0; i < formats.length; i++)
            System.out.println(formats[i]);
    }
}
```

**Output:** 

```java
pattern : {1, number, integer}, {2, number, float#}, {5, date}

Required Formats are : 
null
java.text.DecimalFormat@674dc
java.text.DecimalFormat@5d69738
null
null
java.text.SimpleDateFormat@ce9bf0a5
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            = new MessageFormat("{0, number, #}, {2, date, #.#}, {4, time}");

        // display the result
        System.out.println("pattern : "
                           + mf.toPattern());

        // getting all the format
        // used in MessageFormat Object
        // using getFormatsByArgumentIndex() method
        Format[] formats = mf.getFormatsByArgumentIndex();

        // display the result
        System.out.println("\nRequired Formats are : ");
        for (int i = 0; i < formats.length; i++)
            System.out.println(formats[i]);
    }
}
```

**Output:** 

```java
pattern : {0, number, #}, {2, date, #.#}, {4, time}

Required Formats are : 
java.text.DecimalFormat@674dc
null
java.text.SimpleDateFormat@8918
null
java.text.SimpleDateFormat@8400729
```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/text/message format . html # getformat by arguments index】](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#getFormatsByArgumentIndex--)