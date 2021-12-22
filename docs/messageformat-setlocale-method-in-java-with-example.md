# Java 中的 MessageFormat setLocale()方法，示例

> 原文:[https://www . geesforgeks . org/message format-set locale-method-in-Java-with-example/](https://www.geeksforgeeks.org/messageformat-setlocale-method-in-java-with-example/)

**java.text.MessageFormat** 类的 **setLocale()** 方法用于在该消息格式对象中设置新的区域设置。

**语法:**

```
public void setLocale(Locale locale)
```

**参数**:该方法以新的场所对象为参数。

**返回值:**这个方法没有什么可返回的

以下是说明**设置语言环境()**方法的示例:

**例 1:**

```
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
            = new MessageFormat("{0, number, #}");

        // setting new Locale for
        // message format object
        // using setLocale() method
        mf.setLocale(new Locale("en-US"));

        // getting Locale
        // used in MessageFormat Object
        Locale locale = mf.getLocale();

        // display the result
        System.out.println("Locale is : " + locale);
    }
}
```

**输出:**

```
Locale is : en-us

```

**例 2:**

```
// Java program to demonstrate
// setLocale() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing  MessageFormat
        MessageFormat mf
            = new MessageFormat("{0, number, #}, {2, date, #.#}, {4, time}");

        // setting new Locale for
        // message format object
        // using setLocale() method
        mf.setLocale(new Locale("zh-Hant-TW"));

        // getting Locale
        // used in MessageFormat Object
        Locale locale = mf.getLocale();

        // display the result
        System.out.println("Locale is : " + locale);
    }
}
```

**输出:**

```
Locale is : zh-hant-tw

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/text/message format . html # setlocale-Java . util . locale-](https://docs.oracle.com/javase/9/docs/api/java/text/MessageFormat.html#setLocale-java.util.Locale-)