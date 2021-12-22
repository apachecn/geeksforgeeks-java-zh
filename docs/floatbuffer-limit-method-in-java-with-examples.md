# Java 中的 FloatBuffer limit()方法，带示例

> 原文:[https://www . geeksforgeeks . org/float buffer-limit-in-Java-method-with-examples/](https://www.geeksforgeeks.org/floatbuffer-limit-method-in-java-with-examples/)

[java.nio.FloatBuffer 类](https://www.geeksforgeeks.org/tag/java-floatbuffer/)的 **limit()** 方法用于修改该 FloatBuffer 的限制。此方法将待设置的限制作为参数，并将其设置为此缓冲区的新限制。如果此缓冲区的标记已经定义，并且大于新的指定限制，则不会设置和丢弃此新限制。

**语法:**

```
public final FloatBuffer limit(int *newLimit*)
```

**参数:**该方法取整数型的一个参数*新极限*，该参数是指要设置为缓冲区新极限的极限。

**返回值:**该方法将指定的新限制设置为该缓冲区的新限制后，返回该缓冲区。

以下示例说明了 limit()方法:

**实施例 1:**

```
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating FloatBuffer
        // using allocate() method
        FloatBuffer floatBuffer
            = FloatBuffer.allocate(4);

        // put float value in FloatBuffer
        // using put() method
        floatBuffer.put(20.5f);
        floatBuffer.put(30.5f);

        // print the float buffer
        System.out.println(
            "FloatBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());

        // Limit the floatBuffer
        // using limit() method
        floatBuffer.limit(1);

        // print the float buffer
        System.out.println(
            "\nFloatBuffer after "
            + "setting buffer's limit: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());
    }
}
```

**Output:**

> 设置缓冲器极限前的浮动缓冲器:
> 【20.5，30.5，0.0，0.0】
> 位置:2
> 极限:4
> 
> 设置缓冲器极限后的浮动缓冲器:
> 【20.5，30.5，0.0，0.0】
> 位置:1
> 极限:1

**实施例 2:**

```
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating FloatBuffer
        // using allocate() method
        FloatBuffer floatBuffer
            = FloatBuffer.allocate(5);

        // put float value in FloatBuffer
        // using put() method
        floatBuffer.put(20.5f);
        floatBuffer.put(30.5f);
        floatBuffer.put(40.5f);

        // mark will be going to
        // discarded by limit()
        floatBuffer.mark();

        // print the float buffer
        System.out.println(
            "FloatBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());

        // Limit the floatBuffer
        // using limit() method
        floatBuffer.limit(4);

        // print the double buffer
        System.out.println(
            "\nFloatBuffer before "
            + "setting buffer's limit: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());
    }
}
```

**Output:**

> 设置缓冲器极限前的浮动缓冲器:
> 【20.5，30.5，40.5，0.0，0.0】
> 位置:3
> 极限:5
> 
> 设置缓冲器极限前的浮动缓冲器:
> 【20.5，30.5，40.5，0.0，0.0】
> 位置:3
> 极限:4

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/float buffer . html # limit-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/FloatBuffer.html#limit-int-)