# Java 中的 Bidi getRunLimit()方法，带示例

> 原文:[https://www . geesforgeks . org/bidi-getrunlimit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bidi-getrunlimit-method-in-java-with-examples/)

**java.text.Bidi** 类的 **getRunLimit()** 方法用于提供此 Bidi 实例最后一次运行结束的最后一个字符的(index +1)值。

**语法:**

```
public int getRunLimit(int run)
```

**参数**:该方法接受要检索运行限制的**运行**的索引。

**返回值:**此方法提供最后一次运行的线路的**长度。**

以下是举例说明 **getRunLimit()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// getRunLimit() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi = new Bidi("Tajmahal", 1);

        int index = 1;

        // getting the last character of indexed run
        // using getRunLimit() method
        int level = bidi.getRunLimit(index);

        // display the result
        System.out.println(
            "level of first run is : "
            + level);
    }
}
```

**输出:**

```
level of first run is : 8

```

**例 2:**

```
// Java program to demonstrate
// getRunLimit() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing Bidi
        Bidi bidi = new Bidi("Geeks for Geeks", 1);

        int index = 1;

        // getting the last character of indexed run
        // using getRunLimit() method
        int level = bidi.getRunLimit(index);

        // display the result
        System.out.println(
            "level of first run is : "
            + level);
    }
}
```

**输出:**

```
level of first run is : 15

```

**参考资料:**[https://docs . Oracle . com/javae/9/docs/API/Java/text/bidi . html # info unlike-int-](https://docs.oracle.com/javase/9/docs/api/java/text/Bidi.html#getRunLimit-int-)