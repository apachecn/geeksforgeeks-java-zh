# Java 中的 Level toString()方法，示例

> 原文:[https://www . geesforgeks . org/level-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/level-tostring-method-in-java-with-examples/)

**java.util.logging.Level** 的 **toString()** 方法用于获取代表该级别的字符串值。此方法返回此级别的字符串表示形式。

**语法:**

```
public String toString()

```

**参数:**此方法不接受任何内容。

**返回**:这个方法返回这个级别的字符串表示..

下面的程序说明了 toString()方法:
**程序 1:**

```
// Java program to illustrate toString() method

import java.util.logging.Level;
import java.util.logging.Logger;

public class GFG {

    public static void main(String[] args)
    {

        // Create a Logger
        Logger logger
            = Logger.getLogger(
                        String.class.getName())
                  .getParent();

        // Get level of logger
        Level level
            = logger.getLevel();

        // get string value of level
        String val = level.toString();

        // print result
        System.out.println("toString = "
                           + val);
    }
}
```

**Output:**

```
toString = INFO

```

**程序 2:**

```
// Java program to illustrate toString() method

import java.util.logging.Level;

public class GFG {

    public static void main(String[] args)
    {

        // Get level of logger
        Level level
            = Level.parse("SEVERE");

        // get string representation
        String value = level.toString();

        // print result
        System.out.println("toString = "
                           + value);
    }
}
```

**Output:**

```
toString = SEVERE

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/level . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Level.html#toString())