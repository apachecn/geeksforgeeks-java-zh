# Java 中的 LogRecord getParameters()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-getparameters-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getparameters-method-in-java-with-examples/)

**Java . lang . reflect . log record**的 **getParameters()** 方法用于获取日志消息的参数。这些参数是要插入到这个日志记录的消息中的参数。

**语法:**

```java
public Object[] getParameters()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回**日志消息参数**。如果没有要返回的参数，它可以为空。

下面的程序说明了 getParameters()方法:
**程序 1:**

```java
// Java program to illustrate
// getParameters() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");

        logRecord.setParameters(
            new Object[] {});

        // get object parameters
        Object[] params
            = logRecord.getParameters();

        System.out.println(
            "Object Array length: "
            + params.length);
    }
}
```

**Output:**

```java
Object Array length: 0

```

**程序 2:**

```java
// Java program to illustrate
// getParameters() method

import java.lang.reflect.Method;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("400"),
            "GFG logger");

        Object[] objArr
            = String
                  .class
                  .getDeclaredMethods()[4]
                  .getParameters();
        logRecord.setParameters(objArr);

        // get object parameters
        Object[] params
            = logRecord.getParameters();

        for (int i = 0; i < params.length; i++) {
            System.out.println(params[i]);
        }
    }
}
```

**Output:**

```java
java.lang.Object arg0

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getParameters()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getParameters())