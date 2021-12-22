# Java 中的 LogRecord getResourceBundleName()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-getresourcebundlename-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getresourcebundlename-method-in-java-with-examples/)

**Java . lang . reflect . log record**的 **getResourceBundleName()** 方法用于获取本地化资源包名称。

**语法:**

```java
public String getResourceBundleName()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回**本地化资源包名称**。

下面的程序说明了 getResourceBundleName()方法:
**程序 1:**

```java
// Java program to illustrate
// getResourceBundleName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;
import java.util.ResourceBundle;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");
        logRecord.setResourceBundleName(
            "GFG Bundle");

        // get ResourceBundle Name
        String resourceBundleName
            = logRecord.getResourceBundleName();

        // print the ResourceBundle name
        System.out.println(
            "Resource Bundle = "
            + resourceBundleName);
    }
}
```

**Output:**

```java
Resource Bundle = GFG Bundle

```

**程序 2:**

```java
// Java program to illustrate
// getResourceBundleName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;
import java.util.ResourceBundle;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("600"),
            "GFG Logger");
        logRecord.setResourceBundleName(
            "LOGGER Bundle");

        // get ResourceBundle Name
        String resourceBundleName
            = logRecord.getResourceBundleName();

        // print the ResourceBundle name
        System.out.println(
            "Resource Bundle = "
            + resourceBundleName);
    }
}
```

**Output:**

```java
Resource Bundle = LOGGER Bundle

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getresourcebendlename()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getResourceBundleName())