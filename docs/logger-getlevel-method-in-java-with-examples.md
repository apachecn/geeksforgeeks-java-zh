# Java 中 Logger getLevel()方法，带示例

> 原文:[https://www . geesforgeks . org/logger-get level-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logger-getlevel-method-in-java-with-examples/)

Java 中 **[Logger](https://www.geeksforgeeks.org/logging-in-java/)** 类的 **getLevel()** 方法用于获取为此 Logger 实例指定的日志级别。每个记录器都有特定的日志级别，如果结果为空，这意味着该记录器的有效级别将从其父级继承。

**日志级别:**日志级别控制日志详细信息。它们决定日志文件生成的深度。每个级别都与一个数值相关联，有 7 个基本日志级别和 2 个特殊日志级别。我们需要每次都指定期望的日志记录级别，我们寻求与日志系统进行交互。要了解更多关于日志级别的信息，请参考 T5 日志中的**T3 日志级别**

**语法:**

```
public Level getLevel()

```

**参数:**该方法不接受参数。

**返回值:**该方法返回**级别**，代表记录器级别。

下面的程序说明了 getLevel()方法:
**程序 1:**

```
// Java program to demonstrate
// Logger.getLevel() method

import java.util.logging.Logger;
import java.util.logging.Level;

public class GFG {

    public static void main(String[] args)
    {

        // Create a Logger
        Logger logger
            = Logger.getLogger(
                GFG.class.getName());

        // Get level of logger
        Level level
            = logger.getLevel();

        // If logger level is null
        // then take a level of the parent of logger

        if (level == null && logger.getParent() != null) {
            level = logger.getParent().getLevel();
        }

        System.out.println("Logger Level = " + level);
    }
}
```

**Output:**

```
Logger Level = INFO

```

**程序 2:**

```
// Java program to demonstrate
// Logger.getLevel() method

import java.util.logging.Logger;
import java.util.logging.Level;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create a Logger
        Logger logger
            = Logger.getLogger(
                ArrayList.class.getName());

        // Get level of logger
        Level level = logger.getLevel();

        System.out.println("Logger Level = "
                           + level);
    }
}
```

**Output:**

```
Logger Level = null

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logger . html # getLevel()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Logger.html#getLevel())