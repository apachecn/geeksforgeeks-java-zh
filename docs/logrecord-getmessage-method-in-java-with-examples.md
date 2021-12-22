# Java 中的 LogRecord getMessage()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-get message-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getmessage-method-in-java-with-examples/)

**Java . util . logging . log record**的 **getMessage()** 方法用于获取实际的日志消息，然后从该日志记录中进行本地化或格式化。此消息可能为空，相当于空字符串“”。此返回的消息可能是最终文本或本地化密钥。

**语法:**

```
public String getMessage()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回原始消息字符串。

下面的程序说明了 getMessage()方法:
**程序 1:**

```
// Java program to illustrate getMessage() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("400"),
            "Hi message");

        // get message of LogRecord
        String message = logRecord.getMessage();

        // print result
        System.out.println("Message of Log Record = "
                           + message);
    }
}
```

**Output:**

```
Message of Log Record = Hi message

```

**程序 2:**

```
// Java program to illustrate getMessage() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("WARNING"),
            "Some Warning Message");

        // get message of LogRecord
        String message = logRecord.getMessage();

        // print result
        System.out.println("Message of Log Record = "
                           + message);
    }
}
```

**Output:**

```
Message of Log Record = Some Warning Message

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getMessage()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getMessage())