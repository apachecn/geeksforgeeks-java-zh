# Java 中的 DoubleBuffer order()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-order-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-order-methods-in-java-with-examples/)

[**Java . nio . DoubleBuffer**](https://www.geeksforgeeks.org/tag/java-doublebuffer/)类的 **order()** 方法用于获取这个 double buffer 实例的 ByteOrder。

**语法:**

```java
public abstract ByteOrder order()
```

**返回值:**这个方法返回这个缓冲区的字节顺序。
以下是举例说明 order()方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// order() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of DoubleBuffer
        // and allocating size capacity
        DoubleBuffer db
            = DoubleBuffer.allocate(4);

        // put the double value
        // in the Doublebuffer
        db.put(10.5)
            .put(20.5)
            .put(30.5)
            .put(40.5);

        // rewind the Doublebuffer
        db.rewind();

        // Retrieve the ByteOrder
        // using order() method
        ByteOrder order = db.order();

        // print the double buffer and order
        System.out.println("DoubleBuffer is : "
                           + Arrays.toString(
                                 db.array())
                           + "\nOrder: "
                           + order);
    }
}
```

**Output:** 

```java
DoubleBuffer is : [10.5, 20.5, 30.5, 40.5]
Order: LITTLE_ENDIAN
```