# Java 中的 LogManager getLoggerNames()方法，带示例

> 原文:[https://www . geesforgeks . org/logmanager-getlogernames-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logmanager-getloggernames-method-in-java-with-examples/)

**Java . util . logging . log manager**的 **getLoggerNames()** 方法用于获取已知记录器名称的列表。此方法以枚举对象的形式返回该列表。

**语法:**

```java
public Enumeration getLoggerNames()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法以枚举对象的形式返回已知的**记录器名称列表**列表。

下面的程序说明了 getLoggerNames()方法:

**程序 1:**

```java
// Java program to illustrate
// LogManager getLoggerNames() method

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

        System.out.println("List of Logger Names: ");
        while (listOfNames.hasMoreElements())
            System.out.println(listOfNames.nextElement());
    }
}
```

**输出:**

```java
List of Logger Names: 
global

```

**程序二:**

```java
// Java program to illustrate
// LogManager getLoggerNames() method

import java.util.logging.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogManager object
        LogManager logManager
            = LogManager.getLogManager();

        logManager.addLogger(Logger.getLogger("GFG"));

        Enumeration<String> listOfNames
            = logManager.getLoggerNames();

        System.out.println("\nList of Logger Names: ");
        while (listOfNames.hasMoreElements())
            System.out.println(listOfNames.nextElement());
    }
}
```

**输出:**

```java
List of Logger Names: 
GFG
global

```

**参考:**https://docs . Oracle . com/javase/9/docs/API/Java/util/logging/logmanager . html # getlogger name–