# Java 中的 Bidi isRightToLeft()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-isrighttoleft-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-isrighttoleft-method-in-java-with-examples/)

**java.text.Bidi** 类的 **isRightToLeft()** 方法用于检查它是否同时具有从右到左的直线和基本方向。

**语法:**

```java
public boolean isRightToLeft()
```

**参数**:这个方法不接受任何东西作为参数。

**返回值:**如果此 bidi 同时具有从右到左线和基本方向，则此方法返回**真**，否则返回**假**。

以下是说明 **isRightToLeft()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// isRightToLeft() method

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
        // using isRightToLeft() method
        boolean status = bidi.isRightToLeft();

        // display the result
        if (status)
            System.out.println(
                "Both Line and Base "
                + "direction is right to left");
        else
            System.out.println(
                "Both Line and Base "
                + "direction is not right to left");
    }
}
```

**输出:**

```java
Both Line and Base direction is not right to left 

```

**例 2:**

```java
// Java program to demonstrate
// isRightToLeft() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing 
        // AttributedString Object
        AttributedString attr
            = new AttributedString("GEEkS");

        // adding attribute of langugae
        // using addAttribute() mehtod
        attr.addAttribute(
            AttributedCharacterIterator
                .Attribute
                .LANGUAGE,
            new Locale("ar_QA"));

        // creating and initializing Bidi
        // with AttributedCharacterIterator
        Bidi bidi = new Bidi(attr.getIterator());

        // checking both line and base direction
        // using isRightToLeft() method
        boolean status = bidi.isRightToLeft();

        // display the result
        if (status)
            System.out.println(
                "Both Line and Base "
                + "direction is right to left");
        else
            System.out.println(
                "Both Line and Base "
                + "direction is not right to left");
    }
}
```

**输出:**

```java
Both Line and Base direction is not right to left 

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/bidi . html # isRightToLeft–](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#isRightToLeft--)