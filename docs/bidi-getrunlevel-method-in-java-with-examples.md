# Java 中的 Bidi getRunLevel()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-getrunlevel-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-getrunlevel-method-in-java-with-examples/)

**java.text.Bidi** 类的 **getRunLevel()** 方法用于在只有一个运行状态的情况下为该文本行的第 n 次运行提供级别，它将为该状态提供基本级别。

**语法:**

```java
public int getRunLevel(int run)
```

**参数**:该方法接受逻辑运行的**索引，为其检索运行级别。**

**返回值:**此方法为文本行中的特定运行提供**级别**。

以下是说明 **getRunLevel()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// getRunLevel() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi
            = new Bidi(
                "Geeks For Geeks",
                Bidi.DIRECTION_RIGHT_TO_LEFT);

        // index for which level is needed
        int index = 0;

        // getting the level of run
        // using getRunLevel() method
        int level = bidi.getRunLevel(index);

        // display the result
        System.out.println(
            "level of first run is : "
            + level);
    }
}
```

**输出:**

```java
level of first run is : 2

```

**例 2:**

```java
// Java program to demonstrate
// getRunLevel() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi
            = new Bidi(
                "Geeks For Geeks",
                Bidi.DIRECTION_LEFT_TO_RIGHT);

        // index for which level is needed
        int index = 0;

        // getting the level of run
        // using getRunLevel() method
        int level = bidi.getRunLevel(index);

        // display the result
        System.out.println(
            "level of first run is : "
            + level);
    }
}
```

**输出:**

```java
level of first run is : 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/bidi . html # getRunLevel-int-](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#getRunLevel-int-)