# Java 中的 LogRecord getLoggerName()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-getlogername-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getloggername-method-in-java-with-examples/)

**Java . util . logging . log record**的**getlogginame()**方法用于获取源的日志名称。此方法返回源记录器名称(如果存在),否则返回 null。

**语法:**

```java
public String getLoggerName()

```

**参数:**此方法不接受任何内容。

**返回**:如果存在，该方法返回**源记录器名称**，否则返回空。

下面的程序说明了 getLoggerName()方法:
**程序 1:**

```java
// Java program to illustrate getLoggerName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object with a logger name
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");
        logRecord.setLoggerName("StringLogger");

        // get Logger Name of LogRecord
        String name = logRecord.getLoggerName();

        // print result
        System.out.println("Logger Name = "
                           + name);
    }
}
```

**Output:**

```java
Logger Name = StringLogger

```

**程序 2:**

```java
// Java program to illustrate getLoggerName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object with a logger name
        LogRecord logRecord = new LogRecord(
            Level.parse("400"),
            "GFG Logger");
        logRecord.setLoggerName(String.class.toString());

        // get Logger Name of LogRecord
        String name = logRecord.getLoggerName();

        // print result
        System.out.println("Logger Name = "
                           + name);
    }
}
```

**Output:**

```java
Logger Name = class java.lang.String

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getlogger name()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getLoggerName())