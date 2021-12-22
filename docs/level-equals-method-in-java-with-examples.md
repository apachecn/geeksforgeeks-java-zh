# Java 中 Level 等于()的方法，示例

> 原文:[https://www . geesforgeks . org/level-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/level-equals-method-in-java-with-examples/)

**java.util.logging.Level** 的 **equals()** 方法用来检查这个 Level 对象是否等于传递的对象。如果两个对象相等，那么方法将返回 true，否则返回 false。

**语法:**

```
public boolean equals(Object ox)

```

**参数:**此方法接受一个对象 ox，它是要与之比较的参考对象。

**返回**:当且仅当两个对象具有相同的级别值时，该方法返回 true。

下面的程序说明了 equals()方法:
**程序 1:**

```
// Java program to illustrate equals() method

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
        Level level1
            = logger.getLevel();

        // Create a second Logger
        Logger logger2
            = Logger.getLogger(
                        String.class.getName())
                  .getParent();

        // Get level of second logger
        Level level2
            = logger2.getLevel();

        // apply equal method
        boolean value = level1.equals(level2);

        // print level names
        System.out.println("Both level are equal = "
                           + value);
    }
}
```

**Output:**

```
Both level are equal = true

```

**程序 2:**

```
// Java program to illustrate equals() method

import java.util.ArrayList;
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
        Level level1
            = logger.getLevel();

        // Create a second Logger for ArrayList class
        Logger logger2
            = Logger.getLogger(
                ArrayList.class.getName());

        // Get level of second logger
        Level level2
            = logger2.getLevel();

        // apply equal method
        boolean value = level1.equals(level2);

        // print level names
        System.out.println("Both level are equal = "
                           + value);
    }
}
```

**Output:**

```
Both level are equal = false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/level . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/Level.html#equals(java.lang.Object))