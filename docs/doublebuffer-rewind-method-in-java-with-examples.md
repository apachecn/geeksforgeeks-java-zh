# Java 中的 DoubleBuffer 倒带()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-rewind-in-Java-method-with-examples/](https://www.geeksforgeeks.org/doublebuffer-rewind-method-in-java-with-examples/)

[java.nio.DoubleBuffer 类](https://www.geeksforgeeks.org/tag/java-doublebuffer/)的**倒带()**方法用来倒带这个缓冲区。此方法将位置设置为零，限制不受影响，如果有任何先前标记的位置，将被丢弃。
当需要进行通道写或获取操作时，应调用该方法。这意味着，如果缓冲区数据已经写入，则需要将其复制到另一个数组中。例如:

```java

out.write(buf);    // Writes remaining data
buf.rewind();      // Rewind the buffer
buf.get(array);    // Copy the data into array

```

**语法:**

```java
public final DoubleBuffer rewind()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回这个缓冲区。

以下是说明 rewind()方法的示例:

**实施例 1:**

```java
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating DoubleBuffer
        // using allocate() method
        DoubleBuffer doubleBuffer = DoubleBuffer.allocate(4);

        // put char value in doubleBuffer
        // using put() method
        doubleBuffer.put(10.5);
        doubleBuffer.put(20.5);

        // print the double buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(
                                 doubleBuffer.array())
                           + "\nPosition: "
                           + doubleBuffer.position()
                           + "\nLimit: "
                           + doubleBuffer.limit());

        // rewind the Buffer
        // using rewind() method
        doubleBuffer.rewind();

        // print the doublebuffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(
                                 doubleBuffer.array())
                           + "\nPosition: "
                           + doubleBuffer.position()
                           + "\nLimit: "
                           + doubleBuffer.limit());
    }
}
```

**Output:**

```java
Buffer before operation: [10.5, 20.5, 0.0, 0.0]
Position: 2
Limit: 4

Buffer after operation: [10.5, 20.5, 0.0, 0.0]
Position: 0
Limit: 4

```

**实施例 2:**

```java
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating DoubleBuffer
        // using allocate() method
        DoubleBuffer doubleBuffer
            = DoubleBuffer.allocate(5);

        // put double value in doubleBuffer
        // using put() method
        doubleBuffer.put(10.5);
        doubleBuffer.put(20.5);
        doubleBuffer.put(30.5);

        // mark will be going to discarded by rewind()
        doubleBuffer.mark();

        // print the buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(
                                 doubleBuffer.array())
                           + "\nPosition: "
                           + doubleBuffer.position()
                           + "\nLimit: "
                           + doubleBuffer.limit());

        // Rewind the Buffer
        // using rewind() method
        doubleBuffer.rewind();

        // print the buffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(
                                 doubleBuffer.array())
                           + "\nPosition: "
                           + doubleBuffer.position()
                           + "\nLimit: "
                           + doubleBuffer.limit());
    }
}
```

**Output:**

```java
Buffer before operation: [10.5, 20.5, 30.5, 0.0, 0.0]
Position: 3
Limit: 5

Buffer after operation: [10.5, 20.5, 30.5, 0.0, 0.0]
Position: 0
Limit: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/double buffer . html # rewind–](https://docs.oracle.com/javase/9/docs/api/java/nio/DoubleBuffer.html#rewind--)