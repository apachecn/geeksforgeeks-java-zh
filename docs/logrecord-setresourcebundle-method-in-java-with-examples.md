# Java 中的 LogRecord setResourceBundle()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-setresourcebund-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setresourcebundle-method-in-java-with-examples/)

**Java . util . logging . log record**的 **setResourceBundle()** 方法用于设置本地化资源包。用于本地化此日志记录的消息的资源包。

**语法:**

```
public void setResourceBundle(ResourceBundle bundle)

```

**参数:**该方法接受**束**为定位束，可以为空。

**返回**:此方法不返回任何内容。

下面的程序说明了 setResourceBundle()方法:
**程序 1:**

```
// Java program to illustrate setResourceBundle() method

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

        // Create ResourceBundle using getBundle
        // myResource is a properties file
        ResourceBundle bundle
            = ResourceBundle
                  .getBundle("myResource");

        // set ResourceBundle
        logRecord.setResourceBundle(bundle);

        // print the ResourceBundle details
        System.out.println(
            "Resource Bundle = "
            + logRecord
                  .getResourceBundle()
                  .getBaseBundleName());
    }
}
```

**Output:**

```
Resource Bundle = myResource

```

**程序 2:**

```
// Java program to illustrate setResourceBundle() method

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

        // Create ResourceBundle having null value
        ResourceBundle bundle
            = null;

        // set ResourceBundle
        logRecord.setResourceBundle(bundle);

        // print the ResourceBundle details
        System.out.println(
            "Resource Bundle = "
            + logRecord.getResourceBundle());
    }
}
```

**Output:**

```
Resource Bundle = null

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/logging/logrecord . html # setresourcebund(Java . util . resourcebund)](https://docs.oracle.com/javase/8/docs/api/java/util/logging/LogRecord.html#setResourceBundle(java.util.ResourceBundle))