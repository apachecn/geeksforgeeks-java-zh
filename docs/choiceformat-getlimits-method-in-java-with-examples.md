# 用示例选择 Java 中的 getLimits()方法

> 原文:[https://www . geesforgeks . org/choice format-get limits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/choiceformat-getlimits-method-in-java-with-examples/)

**[Java . text . choice format](https://www.geeksforgeeks.org/tag/java-choiceformat/)**类的 **getLimits()** 方法用于在初始化时获取 choice 格式对象的附加限制。它返回带有限制的双精度类型的数组。

**语法:**

```java
public double[] getLimits()
```

**参数**:此方法不接受任何参数。

**返回值:**此方法返回附加到选择格式对象的限制。

以下是说明 **getLimits()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate getLimits() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing ChoiceFormat
        ChoiceFormat cf
            = new ChoiceFormat(
                "4#wed| 5#thu | 6#fri | 7#sat");

        // getting limit attached to the ChoiceFormat
        // using getLimits() method
        double[] format = cf.getLimits();

        // display the result
        System.out.print("Limit: "
                         + Arrays.toString(format));
    }
}
```

**输出:**

```java
Limit: [4.0, 5.0, 6.0, 7.0]

```

**例 2:**

```java
// Java program to demonstrate getLimits() method

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
            = { "add", "sub", "multiply", "divide" };

        // creating and initializing ChoiceFormat
        ChoiceFormat cf
            = new ChoiceFormat(limit, format);

        // getting limit attached to the ChoiceFormat
        // using getLimits() method
        double[] forma = cf.getLimits();

        // display the result
        System.out.print("Limit: "
                         + Arrays.toString(format));
    }
}
```

**输出:**

```java
Limit: [add, sub, multiply, divide]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/choice format . html # getLimits–](https://docs.oracle.com/javase/9/docs/api/java/text/ChoiceFormat.html#getLimits--)