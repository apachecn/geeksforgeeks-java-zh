# Java 中的 LogRecord getSourceMethodName()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-getsourcemethod name-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getsourcemethodname-method-in-java-with-examples/)

**Java . lang . reflect . log record**的 **getSourceMethodName()** 方法用于获取据称发出日志记录请求的方法的名称。用于日志记录目的的源方法。

**语法:**

```
public String getSourceMethodName()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回**源方法名**。

下面的程序说明了 getSourceMethodName()方法:
**程序 1:**

```
// Java program to illustrate
// getSourceMethodName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");
        logRecord.setSourceMethodName(
            "MyFirstSourceMethod");

        // get the source method name
        String sourceMethod
            = logRecord.getSourceMethodName();

        // print the method name
        System.out.println(
            "Source Method Name = "
            + sourceMethod);
    }
}
```

**Output:**

```
Source Method Name = MyFirstSourceMethod

```

**程序 2:**

```
// Java program to illustrate
// getSourceMethodName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("600"),
            "GFG Logger");
        logRecord.setSourceMethodName(
            ArrayList
                .class
                .getMethods()[0]
                .getName());

        // get the source method name
        String sourceMethod
            = logRecord.getSourceMethodName();

        // print the method name
        System.out.println(
            "Source Method Name = "
            + sourceMethod);
    }
}
```

**Output:**

```
Source Method Name = add

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getSourceMethodName()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getSourceMethodName())