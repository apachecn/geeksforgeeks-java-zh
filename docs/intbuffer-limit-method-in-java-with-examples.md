# Java 中的 IntBuffer limit()方法，带示例

> 原文:[https://www . geesforgeks . org/int buffer-limit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intbuffer-limit-method-in-java-with-examples/)

[java.nio.IntBuffer 类](https://www.geeksforgeeks.org/tag/java-intbuffer/)的 **limit()** 方法用于修改该 IntBuffer 的限制。此方法将待设置的限制作为参数，并将其设置为此缓冲区的新限制。如果此缓冲区的标记已经定义，并且大于新的指定限制，则不会设置和丢弃此新限制。

**语法:**

```
public final IntBuffer limit(int newLimit)
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
        // defining and allocating IntBuffer
        // using allocate() method
        IntBuffer intBuffer
            = IntBuffer.allocate(4);

        // put int value in IntBuffer
        // using put() method
        intBuffer.put(20);
        intBuffer.put(30);

        // print the int buffer
        System.out.println(
            "IntBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());

        // Limit the intBuffer
        // using limit() method
        intBuffer.limit(1);

        // print the int buffer
        System.out.println(
            "\nintBuffer after "
            + "setting buffer's limit: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());
    }
}
```

**输出:**

```
IntBuffer before setting buffer's limit: [20, 30, 0, 0]
Position: 2
Limit: 4

intBuffer after setting buffer's limit: [20, 30, 0, 0]
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
        // defining and allocating IntBuffer
        // using allocate() method
        IntBuffer intBuffer
            = IntBuffer.allocate(5);

        // put int value in IntBuffer
        // using put() method
        intBuffer.put(20);
        intBuffer.put(30);
        intBuffer.put(40);

        // mark will be going to
        // discarded by limit()
        intBuffer.mark();

        // print the int buffer
        System.out.println(
            "intBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());

        // Limit the intBuffer
        // using limit() method
        intBuffer.limit(4);

        // print the int buffer
        System.out.println(
            "\nintBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());
    }
}
```

**输出:**

```
intBuffer before setting buffer's limit: [20, 30, 40, 0, 0]
Position: 3
Limit: 5

intBuffer before setting buffer's limit: [20, 30, 40, 0, 0]
Position: 3
Limit: 4

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/int buffer . html # limit-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/IntBuffer.html#limit-int-)