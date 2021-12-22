# Java 中的 CharBuffer allocate()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-allocate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-allocate-method-in-java-with-examples/)

**java.nio.CharBuffer 类**的 **allocate()** 方法用于在现有缓冲区旁边分配一个新的 **char buffer** 。新缓冲区的位置将为零。它的极限将是它的容量。它的标记将是未定义的。它的每个元素都将被初始化为零。它将有一个后备数组，并且它的数组偏移量为零。
**语法:**

```java
public static CharBuffer allocate(int capacity)
```

**参数:**该方法以 char 中新缓冲区的**容量**为参数。
**返回值**:该方法返回**新的字符缓冲区**。
**异常:**如果容量为负整数，该方法抛出**IllegalArgumentException**。
下面的程序说明了 allocate()方法:
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

        // Declaring the capacity of the CharBuffer
        char capacity = 10;

        // Creating the CharBuffer

        // creating object of Charbuffer
        // and allocating size capacity
        CharBuffer fb = CharBuffer.allocate(capacity);

        // putting the value in charbuffer
        fb.put('a');
        fb.put(3, 'b');

        // Printing the CharBuffer
        System.out.println("ChartBuffer: "
                           + Arrays.toString(fb.array()));
    }
}
```

**Output:** 

```java
ChartBuffer: [a, , , b, , , , , , ]
```

**示例 2:** 演示 IllegalArgumentException

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        // by negative integer
        int capacity = -10;

        // Creating the CharBuffer
        try {

            // creating object of CharBuffer
            // and allocating size with negative integer
            System.out.println("Trying to allocate a negative integer");

            CharBuffer fb = CharBuffer.allocate(capacity);
        }
        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:** 

```java
Trying to allocate a negative integer
Exception thrown: java.lang.IllegalArgumentException
```