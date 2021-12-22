# Java 中的 CharBuffer position()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-position-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-position-methods-in-java-with-examples/)

**[java.nio.CharBuffer 类](https://www.geeksforgeeks.org/tag/java-charbuffer/)** 的**位置(int newPosition)** 方法用于设置该缓冲区的位置。如果标记被定义并且比新位置大，则它被丢弃。

**语法:**

```
public CharBuffer position(int newPosition)
```

**参数:**该方法以**新位置**为参数，为新位置值。它必须是非负的，并且不大于电流限制。

**返回值:**这个方法返回这个缓冲区。

以下是说明**位置()**方法的例子:

**示例 1:**

```
// Java program to demonstrate
// position() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        char[] carr = { 'a', 'b', 'c', 'd' };

        // creating object of CharBuffer
        // and allocating size capacity
        CharBuffer cb = CharBuffer.wrap(carr);

        // try to set the position at index 2
        // using position() method
        cb.position(2);

        // Set this buffer mark position
        cb.mark();

        // try to set the position at index 4
        // using position() method
        cb.position(4);

        // display position
        System.out.println("position before reset: "
                           + cb.position());

        // try to call reset() to restore
        // to the position we marked
        cb.reset();

        // display position
        System.out.println("position after reset: "
                           + cb.position());
    }
}
```

**输出:**

```
position before reset: 4
position after reset: 2

```

**示例 2:**

```
// Java program to demonstrate
// position() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of CharBuffer
        // and allocating size capacity
        CharBuffer cb = CharBuffer.allocate(4);

        // try to set the position at index 1
        // using position() method
        cb.position(1);

        // putting the value of CharBuffer
        // using append() method
        cb.append('x');

        // try to set the position at index 3
        // using position() method
        cb.position(3);

        // putting the value of CharBuffer
        // using append() method
        cb.append("y");

        // display position
        System.out.println("CharBuffer: "
                           + Arrays.toString(cb.array()));
    }
}
```

**输出:**

```
CharBuffer: [,  x,,  y]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charbuffer . html # position-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#position-int-)