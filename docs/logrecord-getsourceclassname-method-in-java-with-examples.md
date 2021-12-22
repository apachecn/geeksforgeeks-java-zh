# Java 中的 LogRecord getSourceClassName()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-getsourceclass name-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getsourceclassname-method-in-java-with-examples/)

**Java . lang . reflect . log record**的 **getSourceClassName()** 方法用于获取据称发出日志记录请求的类的名称。用于日志记录目的的源类名。

**语法:**

```java
public String getSourceClassName()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回**源类名**。

下面的程序说明了 getSourceClassName()方法:
**程序 1:**

```java
// Java program to illustrate
// getSourceClassName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");
        logRecord.setSourceClassName(
            String.class.getName());

        // get source class name
        String sourceClass
            = logRecord.getSourceClassName();

        // print the class name
        System.out.println(
            "Source class Name = "
            + sourceClass);
    }
}
```

**Output:**

```java
Source class Name = java.lang.String

```

**程序 2:**

```java
// Java program to illustrate
// getSourceClassName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("600"),
            "GFG Logger");
        logRecord.setSourceClassName(
            Object.class.getName());

        // get source class name
        String sourceClass
            = logRecord.getSourceClassName();

        // print the class name
        System.out.println(
            "Source class Name = "
            + sourceClass);
    }
}
```

**Output:**

```java
Source class Name = java.lang.Object

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getSourceClassName()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getSourceClassName())