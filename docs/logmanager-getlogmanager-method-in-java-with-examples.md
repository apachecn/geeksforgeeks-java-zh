# Java 中的 LogManager getLogManager()方法，带示例

> 原文:[https://www . geesforgeks . org/logmanager-getlogmanager-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logmanager-getlogmanager-method-in-java-with-examples/)

**Java . util . logging . LogManager**的 **getLogManager()** 方法用于获取全局 LogManager 对象

**语法:**

```java
public static LogManager getLogManager()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回全局 LogManager 对象。

下面程序说明 getLogManager()方法:

```java
// Java program to illustrate
// LogManager getLogManager() method

import java.util.logging.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogManager object
        LogManager logManager
            = LogManager.getLogManager();

        System.out.println("Global LogManager object: "
                           + logManager);
    }
}
```

**输出:**

```java
Global LogManager object: java.util.logging.LogManager@1540e19d

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/logging/logmanager . html # getLogManager–](https://docs.oracle.com/javase/9/docs/api/java/util/logging/LogManager.html#getLogManager--)