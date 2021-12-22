# Java 中 Logger isLoggable()方法，示例

> 原文:[https://www . geesforgeks . org/logger-islogable-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logger-isloggable-method-in-java-with-examples/)

**isLoggable()** 一个**记录器**类的方法用于返回一个布尔值响应，该响应提供了一个查询的答案，即给定级别的消息是否会被该记录器记录。此检查基于记录器的有效级别，该级别可能从其父级继承。

**语法:**

```
public boolean isLoggable(Level level)

```

**参数:**该方法接受一个参数**级别**，代表消息记录级别。

**返回值:**如果当前正在记录给定的消息级别，该方法返回真。

下面的程序说明了 isLoggable()方法:

**程序 1:**

```
// Java program to demonstrate
// Logger.isLoggable() method

import java.util.logging.*;

public class GFG {

    private static Logger logger
        = Logger.getLogger(
            GFG.class.getName());

    public static void main(String args[])
    {

        // Check if the Level.INFO
        // is currently being logged.
        boolean flag
            = logger.isLoggable(
                Level.INFO);

        // Print value
        System.out.println("The Level.INFO"
                           + " is currently being logged - "
                           + flag);
    }
}
```

**输出:**

```
The Level.INFO is currently being logged - true

```

**程序二:**

```
// Java program to demonstrate
// Logger.isLoggable() method

import java.util.logging.*;

public class GFG {

    private static Logger logger
        = Logger.getLogger(
            GFG.class.getName());

    public static void main(String args[])
    {

        // Check if the Level.OFF
        // is currently being logged.
        boolean flag
            = logger.isLoggable(Level.OFF);

        // Print value
        System.out.println("The Level.OFF"
                           + " is currently being logged - "
                           + flag);
    }
}
```

**输出:**

```
The Level.OFF is currently being logged - true

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logger . html # islogable(Java . util . logging . level)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Logger.html#isLoggable(java.util.logging.Level))