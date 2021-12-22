# Java 中的 LongBuffer limit()方法，带示例

> 原文:[https://www . geesforgeks . org/longbuffer-limit-in-Java-method-with-examples/](https://www.geeksforgeeks.org/longbuffer-limit-method-in-java-with-examples/)

[java.nio.LongBuffer 类](https://www.geeksforgeeks.org/tag/java-longbuffer/)的**极限()**方法用来修改这个 LongBuffer 的极限。此方法将待设置的限制作为参数，并将其设置为此缓冲区的新限制。如果此缓冲区的标记已经定义，并且大于新的指定限制，则不会设置和丢弃此新限制。

**语法:**

```
public final LongBuffer limit(int newLimit)
```

**参数:**该方法取整数型的一个参数*新极限*，该参数是指要设置为缓冲区新极限的极限。

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
        // defining and allocating LongBuffer
        // using allocate() method
        LongBuffer longBuffer
            = LongBuffer.allocate(4);

        // put long value in longBuffer
        // using put() method
        longBuffer.put(20);
        longBuffer.put(30);

        // print the long buffer
        System.out.println(
            "LongBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());

        // Limit the longBuffer
        // using limit() method
        longBuffer.limit(1);

        // print the long buffer
        System.out.println(
            "\nLongBuffer after "
            + "setting buffer's limit: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());
    }
}
```

**输出:**

```
LongBuffer before setting buffer's limit: [20, 30, 0, 0]
Position: 2
Limit: 4

LongBuffer after setting buffer's limit: [20, 30, 0, 0]
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
        // defining and allocating LongBuffer
        // using allocate() method
        LongBuffer longBuffer
            = LongBuffer.allocate(5);

        // put double value in LongBuffer
        // using put() method
        longBuffer.put(20);
        longBuffer.put(30);
        longBuffer.put(40);

        // mark will be going to
        // discarded by limit()
        longBuffer.mark();

        // print the long buffer
        System.out.println(
            "LongBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());

        // Limit the longBuffer
        // using limit() method
        longBuffer.limit(4);

        // print the long buffer
        System.out.println(
            "\nLongBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());
    }
}
```

**输出:**

```
LongBuffer before setting buffer's limit: [20, 30, 40, 0, 0]
Position: 3
Limit: 5

LongBuffer before setting buffer's limit: [20, 30, 40, 0, 0]
Position: 3
Limit: 4

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/longbuffer . html # rewind–](https://docs.oracle.com/javase/9/docs/api/java/nio/LongBuffer.html#rewind--)