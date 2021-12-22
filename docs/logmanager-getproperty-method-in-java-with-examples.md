# Java 中的 LogManager getProperty()方法，带示例

> 原文:[https://www . geesforgeks . org/log manager-getproperty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logmanager-getproperty-method-in-java-with-examples/)

**Java . util . logging . LogManager**的 **getProperty()** 方法用于获取这个 LogManager 实例中指定 propertyName 的值。如果这个属性存在，这个方法将在这个日志管理器中获取它。如果它不存在，则此方法返回 null。

**语法:**

```java
public String getProperty(String propertyName)

```

**参数:**这个方法接受一个参数**属性名**，这是要在这个日志管理器实例中获取的属性的名称。

**返回值:**该方法返回该日志管理器中该属性的**名称(如果存在的话)。如果它不存在，则此方法返回 null。**

下面程序举例说明 getProperty()方法:

```java
// Java program to illustrate
// LogManager getProperty() method

import java.util.logging.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogManager object
        LogManager logManager
            = LogManager.getLogManager();

        String propertyName = "GFG";
        System.out.println(
            "\nGet Property value of "
            + propertyName + ": "
            + logManager.getProperty(propertyName));

        propertyName = "Global";
        System.out.println(
            "\nGet Property value of "
            + propertyName + ": "
            + logManager.getProperty(propertyName));
    }
}
```

**输出:**

```java
Get Property value of GFG: null

Get Property value of Global: null

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/logging/logmanager . html # getProperty-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/logging/LogManager.html#getProperty-java.lang.String-)