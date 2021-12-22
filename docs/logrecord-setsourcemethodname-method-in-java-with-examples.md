# Java 中的 LogRecord setSourceMethodName()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-setsourcemethod name-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setsourcemethodname-method-in-java-with-examples/)

**Java . util . logging . log record**的 **setSourceMethodName()** 方法用于设置据称发出日志请求的方法的名称。必须通过此方法设置日志记录中用于日志记录目的的源方法名称。

**语法:**

```java
public void setSourceMethodName(String sourceMethodName)

```

**参数:**该方法接受**源方法名**作为参数，该参数是源方法名。它也可以为空。

**返回**:此方法不返回任何内容。

下面的程序说明了 setSourceMethodName()方法:
**程序 1:**

```java
// Java program to illustrate
// setSourceMethodName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;
public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");

        // set source method
        logRecord
            .setSourceMethodName(
                "MyFirstSourceMethod");

        // print the method name
        System.out.println(
            "Source method Name = "
            + logRecord.getSourceMethodName());
    }
}
```

**Output:**

```java
Source method Name = MyFirstSourceMethod

```

**程序 2:**

```java
// Java program to illustrate
// setSourceMethodName() method

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

        // set a method from ArrayList class
        // as source method
        logRecord.setSourceMethodName(
            ArrayList
                .class
                .getMethods()[0]
                .getName());

        // print the method name
        System.out.println(
            "Source method Name = "
            + logRecord.getSourceMethodName());

        // now set null as method name
        logRecord.setSourceMethodName(null);

        // print the method name
        System.out.println(
            "Now new Source method Name = "
            + logRecord.getSourceMethodName());
    }
}
```

**Output:**

```java
Source method Name = add
Now new Source method Name = null

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # setSourceMethodName(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#setSourceMethodName(java.lang.String))