# Java 中的 Level getName()方法，带示例

> 原文:[https://www . geesforgeks . org/level-getname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/level-getname-method-in-java-with-examples/)

使用 **java.util.logging.Level** 的 **getName()** 方法获取该级别的非本地化字符串名称。此方法返回此方法的名称。

**语法:**

```
public String getName()

```

**参数:**此方法不接受任何内容。

**返回**:该方法返回该级别的非本地化名称。

以下程序说明 getName()方法:
**程序 1:**

```
// Java program to illustrate getName() method

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

        // get Level name
        String name = level.getName();

        // print level names
        System.out.println("Level Name = "
                           + name);
    }
}
```

**Output:**

```
Level Name = INFO

```

**程序 2:**

```
// Java program to illustrate getName() method

import java.util.logging.Level;

public class GFG {

    public static void main(String[] args)
    {

        // Get level of logger
        Level level
            = Level.parse("SEVERE");

        // get Level name
        String name = level.getName();

        // print level names
        System.out.println("Level Name = "
                           + name);
    }
}
```

**Output:**

```
Level Name = SEVERE

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/level . html # getName()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Level.html#getName())