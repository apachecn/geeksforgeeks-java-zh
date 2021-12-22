# Java 中的 LogRecord getLevel()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-get level-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getlevel-method-in-java-with-examples/)

**Java . util . logging . LogRecord**的 **getLevel()** 方法用于获取当前 log record 对象的日志消息级别，例如 Level.Info

**语法:**

```
public Level getLevel()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回日志消息级别。

以下程序说明 getLevel()方法:
**程序 1:**

```
// Java program to illustrate getLevel() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("400"),
            "Hi message");

        // get level of LogRecord
        Level lvl = logRecord.getLevel();

        // print result
        System.out.println("Level of Log Record = "
                           + lvl);
    }
}
```

**Output:**

```
Level of Log Record = FINER

```

**程序 2:**

```
// Java program to illustrate getLevel() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("WARNING"),
            "Some Warning Message");

        // get level of LogRecord
        Level lvl = logRecord.getLevel();

        // print result
        System.out.println("Level of Log Record = "
                           + lvl);
    }
}
```

**Output:**

```
Level of Log Record = WARNING

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getLevel()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getLevel())