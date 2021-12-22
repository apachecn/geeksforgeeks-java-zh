# Java 中的 LogRecord setResourceBundleName()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-setresourcebendlename-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setresourcebundlename-method-in-java-with-examples/)

**Java . util . logging . log record**的 **setResourceBundleName()** 方法用于设置本地化资源包名称。

**语法:**

```java
public void setResourceBundleName(String name)

```

**参数:**该方法接受字符串格式本地化包名称的**名称**。它也可以为空。

**返回**:此方法不返回任何内容。

下面的程序说明了 setResourceBundleName()方法:
**程序 1:**

```java
// Java program to illustrate
// setResourceBundleName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.SEVERE,
                            "Hello Logger");

        // set ResourceBundle Name
        logRecord
            .setResourceBundleName(
                "MyResource Bundle");

        // print the ResourceBundle Name
        System.out.println(
            "Resource Bundle Name= "
            + logRecord.getResourceBundleName());
    }
}
```

**Output:**

```java
Resource Bundle Name= MyResource Bundle

```

**程序 2:**

```java
// Java program to illustrate
// setResourceBundleName() method

import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord
            = new LogRecord(Level.INFO,
                            "GFG Logger");

        // set ResourceBundle Name
        logRecord.setResourceBundleName(null);

        // print the ResourceBundle Name
        System.out.println(
            "Resource Bundle Name= "
            + logRecord.getResourceBundleName());
    }
}
```

**Output:**

```java
Resource Bundle Name= null

```

**参考文献:**T2