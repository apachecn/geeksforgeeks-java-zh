# Java 中的 LogRecord setSourceClassName()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-setsourceclass name-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setsourceclassname-method-in-java-with-examples/)

**Java . util . logging . log record**的 **setSourceClassName()** 方法用于设置据称发出日志请求的类的名称。用于日志记录目的的源类名必须通过这个方法来设置。

**语法:**

```
public void setSourceClassName(String sourceClassName)

```

**参数:**该方法接受**源类名**作为参数，即源类名。它也可以为空。

**返回**:此方法不返回任何内容。

下面的程序说明了 setSourceClassName()方法:
**程序 1:**

```
// Java program to illustrate
// setSourceClassName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;
public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");

        // set String class as source class
        logRecord.setSourceClassName(
            String.class.getName());

        // print the class name
        System.out.println(
            "Source class Name = "
            + logRecord.getSourceClassName());
    }
}
```

**Output:**

```
Source class Name = java.lang.String

```

**程序 2:**

```
// Java program to illustrate
// setSourceClassName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.INFO,
                            "GFG Logger");

        // set ArrayList class as source class
        logRecord.setSourceClassName(
            ArrayList
                .class
                .getName());

        // print the class name
        System.out.println(
            "Source class Name = "
            + logRecord.getSourceClassName());

        // now set null as class name
        logRecord.setSourceClassName(null);

        // print the class name
        System.out.println(
            "Now new Source class Name = "
            + logRecord.getSourceClassName());
    }
}
```

**Output:**

```
Source class Name = java.util.ArrayList
Now new Source class Name = null

```

**参考文献:**T2