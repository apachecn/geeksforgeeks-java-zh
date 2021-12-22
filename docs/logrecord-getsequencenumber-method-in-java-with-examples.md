# Java 中的 LogRecord getSequenceNumber()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-getsequencenumber-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getsequencenumber-method-in-java-with-examples/)

**Java . lang . reflect . log record**的 **getSequenceNumber()** 方法用于获取日志记录的序列号，以便进行日志记录。

**语法:**

```java
public long getSequenceNumber()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回**序号**。

下面的程序说明了 getSequenceNumber()方法:
**程序 1:**

```java
// Java program to illustrate
// getSequenceNumber() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(long[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");
        logRecord.setSequenceNumber(1213425);

        // get SequenceNumber
        long number
            = logRecord.getSequenceNumber();

        // print the SequenceNumber
        System.out.println(
            "SequenceNumber = "
            + number);
    }
}
```

**Output:**

```java
SequenceNumber = 1213425

```

**程序 2:**

```java
// Java program to illustrate
// getSequenceNumber() method

import java.util.logging.Level;
import java.util.logging.LogRecord;
import java.util.*;

public class GFG {

    public static void main(long[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("1200"),
            "HI Logger");
        logRecord.setSequenceNumber(9243254365L);

        // get SequenceNumber
        long number
            = logRecord.getSequenceNumber();

        // print the SequenceNumber
        System.out.println(
            "SequenceNumber = "
            + number);
    }
}
```

**Output:**

```java
SequenceNumber = 9243254365

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getSequenceNumber()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getSequenceNumber())