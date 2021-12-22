# Java 中的 Bidi getBaseLevel()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-getbaselevel-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-getbaselevel-method-in-java-with-examples/)

**java.text.Bidi** 类的 **getBaseLevel()** 方法用来获取这个 Bidi 类实例的基级别。基本级别是指此 Bidi 实例的基本级别是“从左到右”还是“从右到左”。

**语法:**

```java
public int getBaseLevel()
```

**参数**:这个方法不接受任何东西作为参数。

**返回值:**此方法用于提供 0 表示从左到右的基本级别，1 表示从右到左的基本级别。

以下是说明 **getLength()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// getBaseLevel() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi = new Bidi("Geeks for Geeks", 0);

        // getting base level
        // using getBaseLevel() method
        if (bidi.getBaseLevel())
            System.out.println("Base level is "
                               + "right to left");
        else
            System.out.println("Base level is "
                               + "left to right");
    }
}
```

**输出:**

```java
Base level is right to left

```

**例 2:**

```java
// Java program to demonstrate
// getBaseLevel() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        // with base direction
        Bidi bidi
            = new Bidi(
                "Tajmahal",
                Bidi.DIRECTION_LEFT_TO_RIGHT);

        // getting base level
        // using getBaseLevel() method
        if (bidi.getBaseLevel())
            System.out.println("Base level is "
                               + "right to left");
        else
            System.out.println("Base level is "
                               + "left to right");
    }
}
```

**输出:**

```java
Base level is left to right

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/bidi . html # getBaseLevel–](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#getBaseLevel--)