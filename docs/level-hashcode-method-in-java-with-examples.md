# Java 中的级别 hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/level-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/level-hashcode-method-in-java-with-examples/)

使用 **java.util.logging.Level** 的 **hashCode()** 方法获取 Level 对象的 hashCode。如果对象没有改变，hashcode 总是相同的。Hashcode 是 JVM 在创建对象时生成的唯一代码。我们可以使用 hashcode 对 hash 相关算法进行一些操作，比如 hashtable、hashmap 等。我们可以搜索一个具有唯一代码的对象。

**语法:**

```java
public int hashCode()

```

**参数:**此方法不接受任何内容。

**返回**:该方法返回一个整数值，代表该级别的哈希值。

下面的程序说明了 hashCode()方法:
**程序 1:**

```java
// Java program to illustrate hashCode() method

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

        // get hashCode
        int val = level.hashCode();

        // print result
        System.out.println("HashCode = "
                           + val);
    }
}
```

**Output:**

```java
HashCode = 800

```

**程序 2:**

```java
// Java program to illustrate hashCode() method

import java.util.logging.Level;

public class GFG {

    public static void main(String[] args)
    {

        // Get level of logger
        Level level
            = Level.parse("SEVERE");

        // get hash Code
        int value = level.hashCode();

        // print result
        System.out.println("Hash Code = "
                           + value);
    }
}
```

**Output:**

```java
Hash Code = 1000

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/level . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Level.html#hashCode())