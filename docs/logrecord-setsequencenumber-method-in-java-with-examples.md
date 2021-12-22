# Java 中的 LogRecord setSequenceNumber()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-setsequencenumber-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setsequencenumber-method-in-java-with-examples/)

**Java . util . LogRecord**的**设置序列号()**方法用于将序列号设置为 log record，以便进行日志记录。

**语法:**

```
public void setSequenceNumber(long seq)

```

**参数:**该方法接受**序列**作为长型参数，这是我们要设置的序列号。

**返回**:此方法不返回任何内容。

下面的程序说明了 setSequenceNumber()方法:
**程序 1:**

```
// Java program to illustrate
// setSequenceNumber() method

import java.util.logging.Level;
import java.util.logging.LogRecord;
public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");

        // set sequence number
        logRecord.setSequenceNumber(41545412);

        // print the sequence number
        System.out.println(
            "Sequence Number = "
            + logRecord.getSequenceNumber());
    }
}
```

**Output:**

```
Sequence Number = 41545412

```

**程序 2:**

```
// Java program to illustrate
// setSequenceNumber() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class Main {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.INFO,
                            "GFG Logger");

        // set sequence number
        logRecord.setSequenceNumber(96236641);

        // print the sequence number
        System.out.println(
            "Sequence Number = "
            + logRecord.getSequenceNumber());
    }
```

**Output:**

```
Sequence Number = 96236641

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # setSequenceNumber(长)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#setSequenceNumber(long))