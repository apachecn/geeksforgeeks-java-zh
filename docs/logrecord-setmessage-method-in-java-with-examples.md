# Java 中的 LogRecord setMessage()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-set message-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setmessage-method-in-java-with-examples/)

**Java . util . logging . LogRecord**的 **setMessage()** 方法用于在对这个 log record 对象进行本地化或格式化之前设置“原始”日志消息，我们也可以将 null 设置为原始消息。

**语法:**

```java
public void setMessage(String message)

```

**参数:**此方法接受**消息**，为原始消息字符串。

**返回**:此方法不返回任何内容。

下面的程序说明了 setMessage()方法:
**程序 1:**

```java
// Java program to illustrate setMessage() method

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
            "Previous Message: "
            + logRecord.getMessage());

        // set message of the LogRecord
        logRecord.setMessage("GFG Logger");

        // print result
        System.out.println(
            "New Message: "
            + logRecord.getMessage());
    }
}
```

**Output:**

```java
Previous Message: Hi Logger
New Message: GFG Logger

```

**程序 2:**

```java
// Java program to illustrate setMessage() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

import java.util.logging.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.INFO,
            "GFG Logger");

        System.out.println(
            "Previous Message: "
            + logRecord.getMessage());

        // set message of the LogRecord
        logRecord.setMessage(null);

        // print result
        System.out.println(
            "New Message: "
            + logRecord.getMessage());
    }
}
```

**Output:**

```java
Previous Message: GFG Logger
New Message: null

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # setMessage(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#setMessage(java.lang.String))