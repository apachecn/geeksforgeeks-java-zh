# Java 中的 Bidi getRunCount()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-getruncount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-getruncount-method-in-java-with-examples/)

**java.security.Bidi** 类的 **getRunCount()** 方法用于提供 Bidi 文本行中存在的基本级别数。这里我们将只找到一个基本级别，因为我们一次只使用一个基本级别。

**语法:**

```
public int getRunCount()
```

**参数**:这个方法不接受任何东西作为参数。

**返回值:**该方法提供当前运行的**级**数量。

以下是说明 **getRunCount()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// getRunCount() method

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

        // getting the number of level
        // using getRunCount() method
        int lvl = bidi.getRunCount();

        // display the result
        System.out.println(
            "number of levels : "
            + lvl);
    }
}
```

**输出:**

```
number of levels : 1

```

**例 2:**

```
// Java program to demonstrate
// getRunCount() method

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

        // getting the number of level
        // using getRunCount() method
        int lvl = bidi.getRunCount();

        // display the result
        System.out.println(
            "number of levels : "
            + lvl);
    }
}
```

**输出:**

```
number of levels : 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/bidi . html # getRunCount–](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#getRunCount--)