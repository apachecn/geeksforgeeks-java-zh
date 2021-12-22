# Java 中 Level getResourceBundleName()方法，带示例

> 原文:[https://www . geesforgeks . org/level-getresourcebendlename-method-in-Java-with-examples/](https://www.geeksforgeeks.org/level-getresourcebundlename-method-in-java-with-examples/)

使用 **java.util.logging.Level** 的 **getResourceBundleName()** 方法获取该级别对象的本地化资源包名称。如果本地化包存在，则此方法返回包的名称，否则方法返回 null。

**语法:**

```java
public String getResourceBundleName()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回本地化资源包名称。

下面的程序说明了 getResourceBundleName()方法:
**程序 1:**

```java
// Java program to illustrate
// getResourceBundleName() method

import java.util.ResourceBundle;
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

        // get localization resource bundle name
        String name = level.getResourceBundleName();

        // print level localization resource bundle name
        System.out.println("Localization resource"
                           + " bundle name = "
                           + name);
    }
}
```

**Output:**

```java
Localization resource bundle name = sun.util.logging.resources.logging

```

**程序 2:**

```java
// Java program to illustrate
// getResourceBundleName() method

import java.util.logging.Level;

public class GFG {

    public static void main(String[] args)
    {

        // Get level of logger
        Level level
            = Level.parse("SEVERE");

        // get localization resource bundle name
        String name = level.getResourceBundleName();

        // print level localization resource bundle name
        System.out.println("Localization resource"
                           + " bundle name = "
                           + name);
    }
}
```

**Output:**

```java
Localization resource bundle name = sun.util.logging.resources.logging

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/level . html # getresourcebendlename()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Level.html#getResourceBundleName())