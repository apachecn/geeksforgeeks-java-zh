# Java 中的 DoubleBuffer allocate()方法示例

> 原文:[https://www . geesforgeks . org/double buffer-allocate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-allocate-method-in-java-with-examples/)

**java.nio.DoubleBuffer** 类的 **allocate()** 方法用于在现有缓冲区旁边分配一个新的双缓冲区。新缓冲区的位置将为零。它的极限将是它的容量。它的标记将是未定义的。它的每个元素都将被初始化为零。它将有一个后备数组，并且它的数组偏移量为零。
**语法:**

```java
public static DoubleBuffer allocate(int capacity)
```

**参数:**该方法以新缓冲区的**容量**为参数，双倍。
**返回值:**此方法返回**新的双缓冲区。**
**异常:**如果容量为负整数，此方法抛出**IllegalArgumentException**。
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

        // Declaring the capacity of the DoubleBuffer
        int capacity = 10;

        // Creating the DoubleBuffer

        // creating object of Doublebuffer
        // and allocating size capacity
        DoubleBuffer db = DoubleBuffer.allocate(capacity);

        // putting the value in Doublebuffer
        db.put(8.56F);
        db.put(2, 9.61F);

        System.out.println("DoubleBuffer: "
                           + Arrays.toString(db.array()));
    }
}
```

**Output:** 

```java
DoubleBuffer: [8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
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

        // Declaring the capacity of the DoubleBuffer
        // by negative integer
        int capacity = -10;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size with negative integer
            System.out.println("Trying to allocate a negative integer");

            DoubleBuffer db = DoubleBuffer.allocate(capacity);
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