# Java 中的 Bidi isLeftToRight()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-islefttoright-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-islefttoright-method-in-java-with-examples/)

**java.text.Bidi** 类的 **isLeftToRight()** 方法用于检查它是否同时具有从左到右的直线和基本方向。

**语法:**

```
public boolean isLeftToRight()
```

**参数**:这个方法不接受任何东西作为参数。

**返回值:**如果该比迪同时具有左右线和基本方向，则该方法返回**真**，否则返回**假**。

以下是说明 **isLeftToRight()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// isLeftToRight() method

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

        // checking both line and base direction
        // using isLeftToRight() method
        boolean status = bidi.isLeftToRight();

        // display the result
        if (status)
            System.out.println(
                "Both Line and Base "
                + "direction is left to right");
        else
            System.out.println(
                "Both Line and Base "
                + "direction is not left to right ");
    }
}
```

**输出:**

```
Both Line and Base direction is left to right

```

**例 2:**

```
// Java program to demonstrate
// isLeftToRight() method

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
                Bidi.DIRECTION_RIGHT_TO_LEFT);

        // checking both line and base direction
        // using isLeftToRight() method
        boolean status = bidi.isLeftToRight();

        // display the result
        if (status)
            System.out.println(
                "Both Line and Base "
                + "direction is left to right");
        else
            System.out.println(
                "Both Line and Base "
                + "direction is not left to right ");
    }
}
```

**输出:**

```
Both Line and Base direction is not left to right 

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/bidi . html # isLeftToRight–](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#isLeftToRight--)