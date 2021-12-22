# Java 中的 Logger getParent()方法，示例

> 原文:[https://www . geesforgeks . org/logger-get parent-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logger-getparent-method-in-java-with-examples/)

**getParent()** 一个 **Logger** 类的方法用来获取这个 Logger 的父类。如果有一个名为“com.javac.core.api”的 Logger，并且已经创建了一个名为“com.javac”的 Logger，但是不存在 Logger“com . javac . core”，那么在 Logger“com . javac . core . API”上调用 getParent 将返回 Logger“com . javac”。如果我们对命名空间中的根记录器应用 getParent()方法，结果将为空。

**语法:**

```java
public Logger getParent()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回最近的现有父记录器。

下面的程序说明了 getName()方法:
**程序 1:**

```java
// Java program to demonstrate
// Logger.getParent() method

import java.util.logging.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create a logger using getLogger()
        Logger logger
            = Logger.getLogger("com.java.core");

        // Assign other package to logger
        logger = Logger
                     .getLogger("com.java.core.api");

        // Print parent name
        System.out.println("logger name = "
                           + logger
                                 .getParent()
                                 .getName());
    }
}
```

**Output:**

```java
logger name = com.java.core

```

**程序 2:**

```java
// Java program to demonstrate
// Logger.getParent() method

import java.util.logging.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create a logger using getLogger()
        Logger logger = Logger.getLogger("com.java");

        // Assign other package to logger
        logger = Logger.getLogger("com.java.core.api.base");

        // Get Parent logger
        Logger parentLogger = logger.getParent();

        // Print parent name
        System.out.println("Parent logger name = "
                           + parentLogger.getName());
    }
}
```

**Output:**

```java
Parent logger name = com.java

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logger . html # getParent()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Logger.html#getParent())