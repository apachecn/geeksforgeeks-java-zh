# Java 中的 LogRecord setThreadID()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-setthreadid-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setthreadid-method-in-java-with-examples/)

**Java . util . logging . log record**的 **setThreadID()** 方法用于设置消息来源线程的标识符。这个方法有助于识别生成日志消息的线程。

**语法:**

```java
public void setThreadID(int threadID)

```

**参数:**该方法接受**线程号**，该线程号为整数类型的线程号。

**返回**:此方法不返回任何内容。

以下程序说明 setThreadID()方法:
**程序 1:**

```java
// Java program to illustrate
// setThreadID() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");

        // set Thread ID
        logRecord.setThreadID(53677);

        // print Thread ID
        System.out.println(
            "Thread ID = "
            + logRecord.getThreadID());
    }
}
```

**Output:**

```java
Thread ID = 53677

```

**程序 2:**

```java
// Java program to illustrate
// setThreadID() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // start the Thread
        Thread1 thread1 = new Thread1();
        thread1.start();

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");

        // set Thread ID
        logRecord.setThreadID((int)thread1
                                  .getId());

        // print Thread ID
        System.out.println(
            "Thread ID = "
            + logRecord.getThreadID());
    }
}

class Thread1 extends Thread {
    public void run()
    {
        System.out.println("Thread is running...");
    }
}
```

**Output:**

```java
Thread is running...
Thread ID = 8

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # setThreadID(int)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#setThreadID(int))