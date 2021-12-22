# Java 中的 LongBuffer allocate()方法

> 原文:[https://www . geesforgeks . org/longbuffer-allocate-method-in-Java/](https://www.geeksforgeeks.org/longbuffer-allocate-method-in-java/)

**java.nio.LongBuffer 类**的 **allocate()** 方法用于在现有缓冲区旁边分配一个新的*长缓冲区*。新缓冲区的位置将为零。它的极限将是它的容量。它的标记将是未定义的。它的每个元素都将被初始化为零。它将有一个后备数组，并且它的数组偏移量为零。
**语法:**

```java
public static LongBuffer allocate(Long capacity)
```

**参数:**该方法以龙中新缓冲区的*容量*为参数。
**返回值**:此方法返回*新的龙缓冲*。
**异常:**如果容量为负数 Longer，此方法抛出*IllegalArgumentException*。
以下程序说明了 allocate()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int Capacity = 10;

        // Creating the LongBuffer

        // creating object of Longbuffer
        // and allocating size capacity
        LongBuffer ib = LongBuffer.allocate(Capacity);

        // putting the value in Longbuffer
        ib.put(11);
        ib.put(2, 19);

        System.out.println("LongBuffer: "
                           + Arrays.toString(ib.array()));
    }
}
```

**Output:** 

```java
LongBuffer: [11, 0, 19, 0, 0, 0, 0, 0, 0, 0]
```

**程序 2:** 演示非法文档异常

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        // by negative Longer
        int Capacity = -10;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size with negative Longer
            System.out.println("Trying to allocate a Negative Longer");

            LongBuffer ib = LongBuffer.allocate(Capacity);
        }
        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output**

```java
Trying to allocate a Negative Longer
Exception thrown: java.lang.IllegalArgumentException: capacity < 0: (-10 < 0)
```