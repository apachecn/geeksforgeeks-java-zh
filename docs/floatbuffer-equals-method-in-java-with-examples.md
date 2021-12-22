# Java 中的 FloatBuffer 等于()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-equals-method-in-java-with-examples/)

**java.nio.FloatBuffer** 类的 **equals()** 方法用于检查给定的缓冲区是否等于另一个对象。

当且仅当两个浮动缓冲区相等时，

*   它们具有相同的元素类型，
*   它们具有相同数量的剩余元素，并且
*   剩余元素的两个序列，独立于它们的起始位置，是逐点相等的
    。

如果(a = = b)| |(float . isnan(a)& & float . isnan(b))，此方法认为两个 float 元素 a 和 b 相等。值-0.0 和+0.0 被认为是相等的，不像 Float.equals(对象)。

浮动缓冲区不等于任何其他类型的对象。

**语法:**

```java
public boolean equals(Object ob)
```

**参数:**该方法以 **ob** (该缓冲区要与之比较的对象)为参数。

**返回值:**当且仅当该缓冲区等于给定对象时，该方法返回**真**。

以下是说明**等于()**方法的示例:

**实施例 1:**

```java
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the  FloatBuffer 2
        int capacity2 = 10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer 1
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity1);

            // creating object of floatbuffer 2
            // and allocating size capacity
            FloatBuffer fb2 = FloatBuffer.allocate(capacity2);

            // putting the value in floatbuffer 1
            fb1.put(8.56F);
            fb1.put(2, 9.61F);
            fb1.rewind();

            // putting the value in floatbuffer 2
            fb2.put(8.56F);
            fb2.put(2, 9.61F);
            fb2.rewind();

            // print the FloatBuffer 1
            System.out.println(" FloatBuffer 1:  "
                               + Arrays.toString(fb1.array()));

            // print the FloatBuffer 2
            System.out.println(" FloatBuffer 2:  "
                               + Arrays.toString(fb2.array()));

            // checking the equality of both FloatBuffer
            boolean fbb = fb1.equals(fb2);

            // checking if else condition
            if (fbb)
                System.out.println("both are equal");
            else
                System.out.println("both are not equal");
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

**Output:**

```java
FloatBuffer 1:  [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
FloatBuffer 2:  [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
both are equal

```

**实施例 2:**

```java
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the  FloatBuffer 2
        int capacity2 = 5;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer 1
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity1);

            // creating object of floatbuffer 2
            // and allocating size capacity
            FloatBuffer fb2 = FloatBuffer.allocate(capacity2);

            // putting the value in floatbuffer 1
            fb1.put(8.56F);
            fb1.put(2, 9.61F);
            fb1.rewind();

            // putting the value in floatbuffer 2
            fb2.put(8.56F);
            fb2.put(2, 9.61F);
            fb2.rewind();

            // print the FloatBuffer 1
            System.out.println(" FloatBuffer 1:  "
                               + Arrays.toString(fb1.array()));

            // print the FloatBuffer 2
            System.out.println(" FloatBuffer 2:  "
                               + Arrays.toString(fb2.array()));

            // checking the equality of both FloatBuffer
            boolean fbb = fb1.equals(fb2);

            // checking if else condition
            if (fbb)
                System.out.println("both are equal");
            else
                System.out.println("both are not equal");
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

**Output:**

```java
FloatBuffer 1:  [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
FloatBuffer 2:  [8.56, 0.0, 9.61, 0.0, 0.0]
both are not equal

```

**实施例 3:**

```java
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the  FloatBuffer 2
        int capacity2 = 10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer 1
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity1);

            // creating object of floatbuffer 2
            // and allocating size capacity
            FloatBuffer fb2 = FloatBuffer.allocate(capacity2);

            // putting the value in floatbuffer 1
            fb1.put(8.56F);
            fb1.put(2, 9.61F);
            fb1.rewind();

            // putting the value in floatbuffer 2
            fb2.put(8.56F);
            fb2.put(2, 9.61F);
            fb2.put(3, 7.861F);
            fb2.put(4, 4.31F);
            fb2.rewind();

            // print the FloatBuffer 1
            System.out.println(" FloatBuffer 1:  "
                               + Arrays.toString(fb1.array()));

            // print the FloatBuffer 2
            System.out.println(" FloatBuffer 2:  "
                               + Arrays.toString(fb2.array()));

            // checking the equality of both FloatBuffer
            boolean fbb = fb1.equals(fb2);

            // checking if else condition
            if (fbb)
                System.out.println("both are equal");
            else
                System.out.println("both are not equal");
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

**Output:**

```java
FloatBuffer 1:  [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
FloatBuffer 2:  [8.56, 0.0, 9.61, 7.861, 4.31, 0.0, 0.0, 0.0, 0.0, 0.0]
both are not equal

```