# Java 中的 FloatBuffer allocate()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-allocate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-allocate-method-in-java-with-examples/)

**java.nio.FloatBuffer 类**的 **allocate()** 方法用于在现有缓冲区旁边分配一个新的**浮动缓冲区**。新缓冲区的位置将为零。它的极限将是它的容量。它的标记将是未定义的。它的每个元素都将被初始化为零。它将有一个后备数组，并且它的数组偏移量为零。
**语法:**

```java
public static FloatBuffer allocate(int capacity)
```

**参数:**该方法以浮动形式的新缓冲器的**容量**作为参数。
**返回值**:此方法返回**新的浮动缓冲区**。
**异常:**如果容量为负整数，该方法抛出**IllegalArgumentException**。
以下程序说明了 allocate()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer

        // creating object of floatbuffer
        // and allocating size capacity
        FloatBuffer fb = FloatBuffer.allocate(capacity);

        // putting the value in floatbuffer
        fb.put(8.56F);
        fb.put(2, 9.61F);

        System.out.println("FloatBuffer: "
                           + Arrays.toString(fb.array()));
    }
}
```

**Output:** 

```java
FloatBuffer: [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
```

**示例 2:** 演示非法文档异常

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        // by negative integer
        int capacity = -10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size with negative integer
            System.out.println("Trying to allocate a negative integer");

            FloatBuffer fb = FloatBuffer.allocate(capacity);
        }
        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output**

```java
Trying to allocate a negative integer
Exception thrown: java.lang.IllegalArgumentException: capacity < 0: (-10 < 0)

```