# Java 中的 MessageFormat getLocale()方法，示例

> 原文:[https://www . geesforgeks . org/message format-get locale-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-getlocale-method-in-java-with-example/)

**java.text.MessageFormat** 类的 **getLocale()** 方法用于获取该消息格式对象中使用的区域设置。

**语法:**

```java
public Locale getLocale()
```

**参数**:该方法不把任何参数作为参数。

**返回值:**该方法返回该消息格式对象中使用的区域设置。

以下是说明 **getLocale()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getLocale() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {2, date, #.#}, {4, time}");

        // getting Locale
        // used in MessageFormat Object
        // using getLocale() method
        Locale locale = mf.getLocale();

        // display the result
        System.out.println("Locale is : " + locale);
    }
}
```

**输出:**

```java
Locale is : en_US

```

**例 2:**

```java
// Java program to demonstrate
// getLocale() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {2, date, #.#}, {4, time}");

        // setting new Locale for message format object
        mf.setLocale(new Locale("zh-Hant-TW"));

        // getting Locale
        // used in MessageFormat Object
        // using getLocale() method
        Locale locale = mf.getLocale();

        // display the result
        System.out.println("Locale is : " + locale);
    }
}
```

**输出:**

```java
Locale is : zh-hant-tw

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/messageformat . html # getLocale–](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#getLocale--)