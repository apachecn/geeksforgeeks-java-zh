# Java 中的 Bidi getRunStart()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-getrunstart-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-getrunstart-method-in-java-with-examples/)

**java.text.Bidi** 类的 **getRunStart()** 方法用于为此 Bidi 实例提供第 n 次运行开始的第一个字符的索引。

**语法:**

```
public int getRunStart(int run)
```

**参数**:该方法接受要检索运行开始的逻辑运行的**索引。**

**返回值:**该方法为第 n 次逻辑运行提供起始字符的**索引**。

以下是说明 **getRunStart()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// getRunStart() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        // with base direction
        Bidi bidi = new Bidi("Tajmahal", 0);

        int index = 0;

        // getting the start of run for the index 0
        // using getRunStart() method
        int level = bidi.getRunStart(index);

        // display the result
        System.out.println(
            "start of run for index 0 is : "
            + level);
    }
}
```

**输出:**

```
start of run for index 0 is : 0

```

**例 2:**

```
// Java program to demonstrate
// getRunStart() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        // with base direction
        Bidi bidi
            = new Bidi("Geeks for Geeks", 1);

        int index = 0;

        // getting the start of run for the index 0
        // using getRunStart() method
        int level = bidi.getRunStart(index);

        // display the result
        System.out.println(
            "start of run for index 0 is : "
            + level);
    }
}
```

**输出:**

```
start of run for index 0 is : 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/bidi . html # getRunStart-int-](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#getRunStart-int-)