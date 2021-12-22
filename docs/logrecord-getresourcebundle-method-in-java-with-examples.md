# Java 中的 LogRecord getResourceBundle()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-getresourcebund-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getresourcebundle-method-in-java-with-examples/)

使用**Java . lang . reflect . log record**的 **getResourceBundle()** 方法获取本地化资源包。用于本地化此日志记录的消息的资源包。

**语法:**

```
public ResourceBundle getResourceBundle()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回**本地化资源包**。

下面的程序说明了 getResourceBundle()方法:
**程序 1:**

```
// Java program to illustrate
// getResourceBundle() method

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

        logRecord
            .setResourceBundle(
                ResourceBundle
                    .getBundle("myResource"));

        // get ResourceBundle
        ResourceBundle resourceBundle
            = logRecord.getResourceBundle();

        // print the ResourceBundle details
        System.out.println(
            "Resource Bundle = "
            + resourceBundle.getBaseBundleName());
    }
}
```

**Output:**

```
Resource Bundle = myResource

```

**程序 2:**

```
// Java program to illustrate
// getResourceBundle() method

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
        logRecord.setResourceBundle(null);

        // get ResourceBundle
        ResourceBundle resourceBundle
            = logRecord.getResourceBundle();

        // print the ResourceBundle details
        System.out.println(
            "Resource Bundle = "
            + resourceBundle);
    }
}
```

**Output:**

```
Resource Bundle = null

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getresourcebund()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getResourceBundle())