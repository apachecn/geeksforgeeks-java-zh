# Java 中的 LogRecord setLoggerName()方法，带示例

> 原文:[https://www . geeksforgeeks . org/log record-set logger name-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setloggername-method-in-java-with-examples/)

**Java . util . logging . log record**的**setlogginame()**方法用于设置源的记录器名称。此方法返回源记录器名称(如果存在),否则返回 null。

**语法:**

```java
public void setLoggerName(String name)

```

**参数:**该方法接受源记录器**名称**为字符串，也可以为空。

**返回**:此方法不返回任何内容。

下面的程序说明了 setLoggerName()方法:
**程序 1:**

```java
// Java program to illustrate setLoggerName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object with a logger name
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");

        // set String class string value as Logger Name
        logRecord.setLoggerName(String.class.toString());

        // print result
        System.out.println("Logger Name = "
                           + logRecord.getLoggerName());
    }
}
```

**Output:**

```java
Logger Name = class java.lang.String

```

**程序 2:**

```java
// Java program to illustrate setLoggerName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object with a logger name
        LogRecord logRecord = new LogRecord(
            Level.parse("400"),
            "GFG Logger");

        // set null as Logger Name
        logRecord.setLoggerName(null);

        // print result
        System.out.println("Logger Name = "
                           + logRecord.getLoggerName());
    }
}
```

**Output:**

```java
Logger Name = null

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # setlogger name(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#setLoggerName(java.lang.String))