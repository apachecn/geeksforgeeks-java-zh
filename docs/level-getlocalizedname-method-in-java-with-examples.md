# Java 中 Level getLocalizedName()方法，带示例

> 原文:[https://www . geesforgeks . org/level-getlocalized name-method-in-Java-with-examples/](https://www.geeksforgeeks.org/level-getlocalizedname-method-in-java-with-examples/)

使用 **java.util.logging.Level** 的 **getLocalizedName()** 方法获取该级别的本地化字符串名称。此方法返回当前默认区域设置的本地化名称。如果没有可用的本地化信息，则返回未本地化的名称。

**语法:**

```java
public String getLocalizedName()

```

**参数:**此方法不接受任何内容。

**返回**:该方法返回该级别的本地化名称。

下面的程序说明了 getLocalizedName()方法:
**程序 1:**

```java
// Java program to illustrate
// getLocalizedName() method

import java.util.logging.Level;
import java.util.logging.Logger;

public class GFG {

    public static void main(String[] args)
    {

        // Create a Logger
        Logger logger
            = Logger.getLogger(
                        Object.class.getName())
                  .getParent();

        // Get level of logger
        Level level
            = logger.getLevel();

        // get Level localized name
        String name = level.getLocalizedName();

        // print level localized name
        System.out.println("Localized Name = "
                           + name);
    }
}
```

**Output:**

```java
Localized Name = INFO

```

**程序 2:**

```java
// Java program to illustrate
// getLocalizedName() method

import java.util.logging.Level;

public class GFG {

    public static void main(String[] args)
    {

        // Get level of logger
        Level level
            = Level.parse("SEVERE");

        // get Level Localized name
        String name = level.getLocalizedName();

        // print level names
        System.out.println("Localized Name = "
                           + name);
    }
}
```

**Output:**

```java
Localized Name = SEVERE

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/level . html # getlocalized name()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Level.html#getLocalizedName())