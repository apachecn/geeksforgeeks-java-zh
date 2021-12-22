# Java 中的 LogRecord setLevel()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-set level-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setlevel-method-in-java-with-examples/)

**Java . util . logging . log record**的 **setLevel()** 方法用于设置日志消息的级别，例如**级别。此日志记录对象的信息**。

**语法:**

```java
public void setLevel(Level level)

```

**参数:**该方法接受**级别**，即日志消息级别。

**返回**:此方法不返回任何内容。

下面的程序说明了 setLevel()方法:
**程序 1:**

```java
// Java program to illustrate setLevel() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

import java.util.logging.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");

        System.out.println(
            "Previous Level: "
            + logRecord.getLevel().getName());

        // set level of the LogRecord
        logRecord.setLevel(Level.FINEST);

        // print result
        System.out.println(
            "New Level: "
            + logRecord.getLevel().getName());
    }
}
```

**Output:**

```java
Previous Level: INFO
New Level: FINEST

```

**程序 2:**

```java
// Java program to illustrate setLevel() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("400"),
            "GFG Logger");

        System.out.println(
            "Previous Level: "
            + logRecord.getLevel().getName());

        // set level of the LogRecord
        logRecord.setLevel(Level.WARNING);

        // print result
        System.out.println(
            "New Level: "
            + logRecord.getLevel().getName());
    }
}
```

**Output:**

```java
Previous Level: FINER
New Level: WARNING

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # setLevel(Java . util . logging . level)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#setLevel(java.util.logging.Level))