# Java 中的 LogManager getLogger()方法，带示例

> 原文:[https://www . geesforgeks . org/logmanager-getlogger-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logmanager-getlogger-method-in-java-with-examples/)

**Java . util . logging . LogManager**的 **getLogger()** 方法用于在这个 LogManager 实例中获取指定的 Logger。此记录器必须是命名的记录器。这个方法将在这个日志管理器中获取这个日志记录程序，如果它存在的话。如果它不存在，则此方法返回 null。

**语法:**

```java
public Logger getLogger(Logger logger)

```

**参数:**这个方法接受一个参数**记录器**，这是要在这个日志管理器实例中获取的记录器的名称。

**返回值:**该方法返回该日志管理器中该日志记录者的**名称(如果存在)。如果它不存在，则此方法返回 null。**

下面程序举例说明 getLogger()方法:

```java
// Java program to illustrate
// LogManager getLogger() method

import java.util.logging.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogManager object
        LogManager logManager
            = LogManager.getLogManager();

        String LoggerName = "GFG";
        Logger logger
            = Logger.getLogger(LoggerName);
        logManager.addLogger(logger);

        System.out.println("\nList of Logger Names: ");
        Enumeration<String> listOfNames
            = logManager.getLoggerNames();
        while (listOfNames.hasMoreElements())
            System.out.println(listOfNames.nextElement());

        System.out.println(
            "\nGet Logger Name "
            + LoggerName + ": "
            + logManager.getLogger(LoggerName));

        LoggerName = "Geeks";

        System.out.println(
            "\nGet Logger Name "
            + LoggerName + ": "
            + logManager.getLogger(LoggerName));
    }
}
```

**输出:**

```java
List of Logger Names: 
GFG
global

Get Logger Name GFG: java.util.logging.Logger@1540e19d

Get Logger Name Geeks: null

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/logging/logmanager . html # getLogger-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/logging/LogManager.html#getLogger-java.lang.String-)