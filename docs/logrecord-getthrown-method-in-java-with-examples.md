# Java 中的 LogRecord getThrown()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-getthrown-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getthrown-method-in-java-with-examples/)

**Java . lang . reflect . log record**的 **getThrown()** 方法用于获取与日志事件相关联的可抛出。这用于在日志记录中记录异常，该记录可用于记录消息。

**语法:**

```
public Throwable getThrown()

```

**参数:**此方法不接受任何内容。

**返回**:这个方法返回**一个可投掷的**。

以下程序说明 getThrown()方法:
**程序 1:**

```
// Java program to illustrate
// getThrown() method

import java.io.IOException;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.INFO,
                            "GFG Logger");
        logRecord.setThrown(
            new IOException(
                "Error in Input"));

        // get Throwable object
        Throwable throwObj
            = logRecord.getThrown();

        // print result
        System.out.println(
            "throwable object = "
            + throwObj
                  .toString());
    }
}
```

**Output:**

```
throwable object = java.io.IOException: Error in Input

```

**程序 2:**

```
// Java program to illustrate
// getThrown() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.WARNING,
                            "Logger");
        logRecord.setThrown(
            new ArithmeticException());

        // get Throwable object
        Throwable throwObj
            = logRecord.getThrown();

        // print result
        System.out.println(
            "throwable object = "
            + throwObj
                  .toString());
    }
}
```

**Output:**

```
throwable object = java.lang.ArithmeticException

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getThrown()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getThrown())