# Java 中的 Level intValue()方法，示例

> 原文:[https://www . geesforgeks . org/level-int value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/level-intvalue-method-in-java-with-examples/)

使用 **java.util.logging.Level** 的 **intValue()** 方法获取该级别对象的整数值。每个级别都有一个与之关联的整数值。该整数值可用于级别对象之间的高效排序比较。如果我们想在日志记录中使用 level 对象的 int 值进行比较，这个方法会很有帮助。

**语法:**

```java
public int intValue()

```

**参数:**此方法不接受任何内容。

**返回**:该方法返回该级别对象的**整数值**。

以下程序说明了 intValue()方法:
**程序 1:**

```java
// Java program to illustrate
// intValue() method

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

        // get intValue
        int val = level.intValue();

        // print result
        System.out.println("intValue = "
                           + val);
    }
}
```

**Output:**

```java
intValue = 800

```

**程序 2:**

```java
// Java program to illustrate
// intValue() method

import java.util.logging.Level;

public class GFG {

    public static void main(String[] args)
    {

        // Get level of logger
        Level level
            = Level.parse("SEVERE");

        // get int code
        int value = level.intValue();

        // print result
        System.out.println("intValue = "
                           + value);
    }
}
```

**Output:**

```java
intValue = 1000

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/level . html # intValue()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Level.html#intValue())