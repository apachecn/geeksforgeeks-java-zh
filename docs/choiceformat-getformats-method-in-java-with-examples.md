# 用示例选择 Java 中的 getFormats()方法

> 原文:[https://www . geeksforgeeks . org/choice format-get formats-method-in-Java-with-examples/](https://www.geeksforgeeks.org/choiceformat-getformats-method-in-java-with-examples/)

**[Java . text . ChoiceFormat](https://www.geeksforgeeks.org/tag/java-choiceformat/)**类的 **getFormats()** 方法用于在初始化时获取 choice format 对象的附加格式。它提供指定类型的数组。

**语法:**

```
public Object[] getFormats()
```

**参数**:此方法不接受任何参数。

**返回值:**这个方法返回一个指定类型的**数组**，它是附加到 ChoiceFormat 对象的格式。

以下是说明 **getFormats()** 方法的示例:

**例 1:**

```
// Java program to demonstrate
// getFormats() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing ChoiceFormat
        ChoiceFormat cf1
            = new ChoiceFormat(
                "4#wed| 5#thu | 6#fri | 7#sat");

        // getting format attached
        // to the ChoiceFormat
        // using getFormats() method
        String[] format
            = (String[])cf1.getFormats();

        // display the result
        System.out.print("Format: "
                         + Arrays.toString(format));
    }
}
```

**输出:**

```
Format: [wed, thu , fri , sat]

```

**例 2:**

```
// Java program to demonstrate
// getFormats() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing limit
        double[] limit = { 1, 2, 3, 4 };

        // creating and initializing format
        String[] format
            = { "add", "sub",
                "multiply", "divide" };

        // creating and initializing ChoiceFormat
        ChoiceFormat cf
            = new ChoiceFormat(limit, format);

        // getting format attached
        // to the ChoiceFormat
        // using getFormats() method
        String[] forma
            = (String[])cf.getFormats();

        // display the result
        System.out.print("Format: "
                         + Arrays.toString(forma));
    }
}
```

**输出:**

```
Format: [add, sub, multiply, divide]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/choice format . html # getFormats–](https://docs.oracle.com/javase/9/docs/api/java/text/ChoiceFormat.html#getFormats--)