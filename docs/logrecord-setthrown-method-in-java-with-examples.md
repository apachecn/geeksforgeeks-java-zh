# Java 中的 LogRecord setThrown()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-setthrown-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setthrown-method-in-java-with-examples/)

**Java . util . logging . log record**的 **setThrown()** 方法用于与日志事件相关联的可抛出。这用于在日志记录中记录异常，该记录可用于记录消息。

**语法:**

```java
public void setThrown(Throwable thrown)

```

**参数:**该方法接受**抛出的**作为参数，该参数为可抛出对象。它也可以为空。

**返回**:此方法不返回任何内容。

下面的程序说明 setThrown()方法:
**程序 1:**

```java
// Java program to illustrate setThrown() method

import java.io.IOException;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");

        // set throwable object
        logRecord.setThrown(
            new IOException(
                "Error in Input"));

        // print the method name
        System.out.println(
            "throwable object Message = "
            + logRecord.getThrown()
                  .toString());
    }
}
```

**Output:**

```java
throwable object Message = java.io.IOException: Error in Input

```

**程序 2:**

```java
// Java program to illustrate setThrown() method

import java.io.IOException;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");

        // create a throwable object
        Exception exception
            = new ArithmeticException(
                "divide by 0");

        // set throwable object
        logRecord.setThrown(exception);

        // print the result
        System.out.println(
            "throwable object = "
            + logRecord.getThrown()
                  .toString());
    }
}
```

**Output:**

```java
throwable object = java.lang.ArithmeticException: divide by 0

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # setThrown(Java . lang . throwable)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#setThrown(java.lang.Throwable))