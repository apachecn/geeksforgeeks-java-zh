# Java 中的 LogRecord getInstant()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-getinstant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getinstant-method-in-java-with-examples/)

**Java . lang . reflect . log record**的 **getInstant()** 方法用于获取事件发生的这个瞬间，这有助于记录事件的瞬间。

**语法:**

```java
public Instant getInstant()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回事件发生的**瞬间**。

下面的程序说明了 getInstant()方法:
**程序 1:**

```java
// Java program to illustrate getInstant() method

import java.time.Instant;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");
        logRecord
            .setInstant(
                Instant.parse(
                    "1994-04-12T11:54:23.89Z"));

        // get the instant time
        Instant instant = logRecord.getInstant();

        System.out.println("Event Time = "
                           + instant.toString());
    }
}
```

**Output:**

```java
Event Time = 1994-04-12T11:54:23.890Z

```

**程序 2:**

```java
// Java program to illustrate getInstant() method

import java.time.Instant;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");
        logRecord.setInstant(Instant.now());

        // get the instant time
        Instant instant = logRecord.getInstant();

        System.out.println("Event Time = "
                           + instant.toString());
    }
}
```

**Output:**

```java
Event Time = 2019-10-20T19:41:57.803594Z

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getInstant()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getInstant())