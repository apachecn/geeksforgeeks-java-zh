# Java 中的 FloatBuffer slice()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-slice-method-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-slice-method-in-java-with-examples/)

类的 **slice()** 方法用于创建一个**新的浮动缓冲区**，其内容是给定缓冲区内容的共享子序列。
新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然。两个缓冲器的位置、极限和标记值将是独立的。
新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的浮动数量，其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```java
public abstract FloatBuffer slice()
```

**返回值:**该方法返回**新的浮动缓冲区。**
以下是举例说明切片()方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// slice() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb1.put(8.56F);
            fb1.put(9.61F);

            // print the FloatBuffer
            System.out.println("Original FloatBuffer: "
                               + Arrays.toString(fb1.array()));

            // print the FloatBuffer position
            System.out.println("\nposition:  " + fb1.position());

            // print the FloatBuffer capacity
            System.out.println("\ncapacity:  " + fb1.capacity());

            // Creating a shared subsequence buffer of given FloatBuffer
            // using slice() method
            FloatBuffer fb2 = fb1.slice();

            // print the shared subsequence buffer
            System.out.println("\nshared subsequence FloatBuffer: "
                               + Arrays.toString(fb2.array()));

            // print the FloatBuffer position
            System.out.println("\nposition:  " + fb2.position());

            // print the FloatBuffer capacity
            System.out.println("\ncapacity:  " + fb2.capacity());
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**Output**

```java
Original FloatBuffer: [8.56, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

position:  2

capacity:  10

shared subsequence FloatBuffer: [8.56, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

position:  0

capacity:  8
```

**实施例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// slice() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb1.put(8.56F);
            fb1.put(9.61F);
            fb1.put(0.56F);
            fb1.put(3.61F);

            // print the FloatBuffer
            System.out.println("Original FloatBuffer: "
                               + Arrays.toString(fb1.array()));

            // print the FloatBuffer position
            System.out.println("\nposition:  " + fb1.position());

            // print the FloatBuffer capacity
            System.out.println("\ncapacity:  " + fb1.capacity());

            // Creating a shared subsequence buffer of given FloatBuffer
            // using slice() method
            FloatBuffer fb2 = fb1.slice();
            fb2.put(2.34F);
            fb2.put(6.34F);

            // print the shared subsequence buffer
            System.out.println("\nshared subsequence FloatBuffer: "
                               + Arrays.toString(fb2.array()));

            // print the FloatBuffer position
            System.out.println("\nposition:  " + fb2.position());

            // print the FloatBuffer capacity
            System.out.println("\ncapacity:  " + fb2.capacity());
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**Output**

```java
Original FloatBuffer: [8.56, 9.61, 0.56, 3.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

position:  4

capacity:  10

shared subsequence FloatBuffer: [8.56, 9.61, 0.56, 3.61, 2.34, 6.34, 0.0, 0.0, 0.0, 0.0]

position:  2

capacity:  6
```