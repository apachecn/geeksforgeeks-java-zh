# Java 中的 Bidi baseIsLeftToRight()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bidi-baseislefttoright-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-baseislefttoright-method-in-java-with-examples/)

**java.text.Bidi** 类的**base islettoright()**方法用于检查这个 Bidi 实例是否有从左到右的基本方向。

**语法:**

```java
public boolean baseIsLeftToRight()
```

**参数**:这个方法不接受任何东西作为参数。

**返回值:**如果此比迪已经向左到**向右**基本方向，则此方法返回**真**否则返回假。

以下是说明 **getLength()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// baseIsLeftToRight() method

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
                "Geeks For Geeks",
                Bidi.DIRECTION_LEFT_TO_RIGHT);

        // checking base direction
        // using baseIsLeftToRight() method
        boolean status
            = bidi.baseIsLeftToRight();

        // display the result
        if (status)
            System.out.println(
                "Base direction is "
                + "left to right");
        else
            System.out.println(
                "Base direction is "
                + "right to left");
    }
}
```

**输出:**

```java
Base direction is left to right

```

**例 2:**

```java
// Java program to demonstrate
// baseIsLeftToRight() method

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
                Bidi.DIRECTION_RIGHT_TO_LEFT);

        // checking base direction
        // using baseIsLeftToRight() method
        boolean status
            = bidi.baseIsLeftToRight();

        // display the result
        if (status)
            System.out.println(
                "Base direction is "
                + "left to right");
        else
            System.out.println(
                "Base direction is "
                + "right to left");
    }
}
```

**输出:**

```java
Base direction is right to left

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/Bidi . html # baseilesfttoright–](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#baseIsLeftToRight--)