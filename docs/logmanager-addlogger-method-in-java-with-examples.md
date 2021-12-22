# Java 中的 LogManager addLogger()方法，示例

> 原文:[https://www . geesforgeks . org/logmanager-addlogger-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logmanager-addlogger-method-in-java-with-examples/)

**Java . util . logging . LogManager**的 **addLogger()** 方法用于在这个 LogManager 实例中插入指定的 Logger。此记录器必须是命名的记录器。如果日志管理器还不存在，这个方法会在日志管理器中添加这个日志记录器。如果它已经存在，那么这个方法返回 false。

**语法:**

```
public boolean addLogger(Logger logger)

```

**参数:**这个方法接受一个参数 **logger** ，它是要插入到这个 LogManager 实例中的 logger 的名称，如果它还不存在的话。

**返回值:**如果这个记录器已经存在，这个方法返回一个**布尔值** false。否则这个方法不返回任何东西。

**异常:**如果要添加的记录器为空，该方法抛出**空指针异常**。

下面程序举例说明 addLogger()方法:

```
// Java program to illustrate
// LogManager addLogger() method

import java.util.logging.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogManager object
        LogManager logManager
            = LogManager.getLogManager();

        Enumeration<String> listOfNames
            = logManager.getLoggerNames();

        System.out.println("Earlier List of Logger Names: ");
        while (listOfNames.hasMoreElements())
            System.out.println(listOfNames.nextElement());

        String LoggerName = "GFG";

        Logger logger
            = Logger.getLogger(LoggerName);

        System.out.println("Adding Logger: " + LoggerName);
        logManager.addLogger(logger);
        listOfNames = logManager.getLoggerNames();

        System.out.println("\nUpdated List of Logger Names: ");
        while (listOfNames.hasMoreElements())
            System.out.println(listOfNames.nextElement());
    }
}
```

**输出:**

```
Earlier List of Logger Names: 
global

Adding Logger: GFG

Updated List of Logger Names: 
GFG
global

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/logging/logging manager . html # addLogger-Java . util . logging . logger-](https://docs.oracle.com/javase/9/docs/api/java/util/logging/LogManager.html#addLogger-java.util.logging.Logger-)