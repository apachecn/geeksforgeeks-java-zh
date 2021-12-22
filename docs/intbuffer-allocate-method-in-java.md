# Java 中的 IntBuffer allocate()方法

> 原文:[https://www . geesforgeks . org/int buffer-allocate-method-in-Java/](https://www.geeksforgeeks.org/intbuffer-allocate-method-in-java/)

**java.nio.IntBuffer 类**的 **allocate()** 方法用于在现有缓冲区旁边分配一个新的 **int buffer** 。新缓冲区的位置将为零。它的极限将是它的容量。它的标记将是未定义的。它的每个元素都将被初始化为零。它将有一个后备数组，并且它的数组偏移量为零。

**语法:**

```java
public static IntBuffer allocate(int capacity)
```

**参数:**该方法以新缓冲区的**容量**为参数，以 int 为单位。

**返回值**:该方法返回**新的 int 缓冲区**。

**异常:**如果容量为负整数，该方法抛出 **IllegalArgumentException** 。

下面的程序说明了 allocate()方法:

**实施例 1:**

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the IntBuffer
        int Capacity = 10;

        // Creating the IntBuffer

        // creating object of intbuffer
        // and allocating size capacity
        IntBuffer ib = IntBuffer.allocate(Capacity);

        // putting the value in intbuffer
        ib.put(11);
        ib.put(2, 19);

        System.out.println("IntBuffer: "
                           + Arrays.toString(ib.array()));
    }
}
```

**Output:**

```java
IntBuffer: [11, 0, 19, 0, 0, 0, 0, 0, 0, 0]

```

**示例 2:** 演示 IllegalArgumentException

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the IntBuffer
        // by negative integer
        int Capacity = -10;

        // Creating the IntBuffer
        try {

            // creating object of intbuffer
            // and allocating size with negative integer
            System.out.println("Trying to allocate a Negative Integer");

            IntBuffer ib = IntBuffer.allocate(Capacity);
        }
        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
Trying to allocate a Negative Integer
Exception thrown: java.lang.IllegalArgumentException

```