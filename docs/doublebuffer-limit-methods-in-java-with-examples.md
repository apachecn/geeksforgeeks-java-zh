# Java 中的 DoubleBuffer limit()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-limit-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-limit-methods-in-java-with-examples/)

[java.nio.DoubleBuffer 类](https://www.geeksforgeeks.org/tag/java-doublebuffer/)的 **limit()** 方法用于修改该 DoubleBuffer 的限制。此方法将待设置的限制作为参数，并将其设置为此缓冲区的新限制。如果此缓冲区的标记已经定义，并且大于新的指定限制，则不会设置和丢弃此新限制。

**语法:**

```
public final DoubleBuffer limit(int newLimit)
```

**返回值:**该方法将指定的新限制设置为该缓冲区的新限制后，返回该缓冲区。

以下是举例说明 limit()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating DoubleBuffer
        // using allocate() method
        DoubleBuffer doubleBuffer
            = DoubleBuffer.allocate(4);

        // put double value in doubleBuffer
        // using put() method
        doubleBuffer.put(20.5);
        doubleBuffer.put(30.5);

        // print the double buffer
        System.out.println("DoubleBuffer before "
                           + "setting buffer's limit: "
                           + Arrays.toString(
                                 doubleBuffer.array())
                           + "\nPosition: "
                           + doubleBuffer.position()
                           + "\nLimit: "
                           + doubleBuffer.limit());

        // Limit the doubleBuffer
        // using limit() method
        doubleBuffer.limit(1);

        // print the double buffer
        System.out.println("\nDoubleBuffer after "
                           + "setting buffer's limit: "
                           + Arrays.toString(
                                 doubleBuffer.array())
                           + "\nPosition: "
                           + doubleBuffer.position()
                           + "\nLimit: "
                           + doubleBuffer.limit());
    }
}
```

**输出:**

```
DoubleBuffer before setting buffer's limit: [20.5, 30.5, 0.0, 0.0]
Position: 2
Limit: 4

DoubleBuffer after setting buffer's limit: [20.5, 30.5, 0.0, 0.0]
Position: 1
Limit: 1

```

**示例 2:**

```
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating DoubleBuffer
        // using allocate() method
        DoubleBuffer doubleBuffer
            = DoubleBuffer.allocate(5);

        // put double value in DoubleBuffer
        // using put() method
        doubleBuffer.put(20.5);
        doubleBuffer.put(30.5);
        doubleBuffer.put(40.5);

        // mark will be going to
        // discarded by limit()
        doubleBuffer.mark();

        // print the double buffer
        System.out.println("DoubleBuffer before "
                           + "setting buffer's limit: "
                           + Arrays.toString(
                                 doubleBuffer.array())
                           + "\nPosition: "
                           + doubleBuffer.position()
                           + "\nLimit: "
                           + doubleBuffer.limit());

        // Limit the doubleBuffer
        // using limit() method
        doubleBuffer.limit(4);

        // print the double buffer
        System.out.println("\nDoubleBuffer before "
                           + "setting buffer's limit: "
                           + Arrays.toString(
                                 doubleBuffer.array())
                           + "\nPosition: "
                           + doubleBuffer.position()
                           + "\nLimit: "
                           + doubleBuffer.limit());
    }
}
```

**输出:**

```
DoubleBuffer before setting buffer's limit: [20.5, 30.5, 40.5, 0.0, 0.0]
Position: 3
Limit: 5

DoubleBuffer before setting buffer's limit: [20.5, 30.5, 40.5, 0.0, 0.0]
Position: 3
Limit: 4

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/double buffer . html # limit-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/DoubleBuffer.html#limit-int-)