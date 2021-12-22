# Java 中的字节缓冲等于()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-equals-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **equals()** 方法用于检查给定的缓冲区是否等于另一个对象。

当且仅当两个字节缓冲区相等时，

*   它们具有相同的元素类型，
*   它们具有相同数量的剩余元素，并且
*   剩余元素的两个序列，不管它们的起始位置如何，都是逐点相等的。

字节缓冲区不等于任何其他类型的对象。

**语法:**

```
public boolean equals(Object ob)
```

**参数:**该方法以 ob(该缓冲区要与之比较的对象)为参数。

**返回值:**当且仅当该缓冲区等于给定对象时，该方法返回真。

以下是说明*等于()*方法的示例:

**实施例 1:**

```
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer 1
        int capacity1 = 5;

        // Declaring the capacity of the  ByteBuffer 2
        int capacity2 = 5;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer 1
            // and allocating size capacity
            ByteBuffer bb1 = ByteBuffer.allocate(capacity1);

            // creating object of ByteBuffer 2
            // and allocating size capacity
            ByteBuffer bb2 = ByteBuffer.allocate(capacity2);

            // putting the int to byte typecast value in ByteBuffer 1
            bb1.put((byte)20);
            bb1.put((byte)30);
            bb1.put((byte)40);
            bb1.rewind();

            // putting the value in ByteBuffer 2
            bb2.put((byte)20);
            bb2.put((byte)30);
            bb2.put((byte)40);
            bb2.rewind();

            // print the ByteBuffer 1
            System.out.println(" ByteBuffer 1:  "
                               + Arrays.toString(bb1.array()));

            // print the ByteBuffer 2
            System.out.println(" ByteBuffer 2:  "
                               + Arrays.toString(bb2.array()));

            // checking the equality of both ByteBuffer
            boolean b = bb1.equals(bb2);

            // checking if else condition
            if (b)
                System.out.println(" both are equal");
            else
                System.out.println(" both are not equal");
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ByteBuffer 1:  [20, 30, 40, 0, 0]
 ByteBuffer 2:  [20, 30, 40, 0, 0]
 both are equal

```

**实施例 2:**

```
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer 1
        int capacity1 = 5;

        // Declaring the capacity of the  ByteBuffer 2
        int capacity2 = 3;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer 1
            // and allocating size capacity
            ByteBuffer bb1 = ByteBuffer.allocate(capacity1);

            // creating object of ByteBuffer 2
            // and allocating size capacity
            ByteBuffer bb2 = ByteBuffer.allocate(capacity2);

            // putting the int to byte typecast value in ByteBuffer 1
            bb1.put((byte)20);
            bb1.put((byte)30);
            bb1.put((byte)40);
            bb1.rewind();

            // putting the value in ByteBuffer 2
            bb2.put((byte)20);
            bb2.put((byte)30);
            bb2.put((byte)40);
            bb2.rewind();

            // print the ByteBuffer 1
            System.out.println(" ByteBuffer 1:  "
                               + Arrays.toString(bb1.array()));

            // print the ByteBuffer 2
            System.out.println(" ByteBuffer 2:  "
                               + Arrays.toString(bb2.array()));

            // checking the equality of both ByteBuffer
            boolean b = bb1.equals(bb2);

            // checking if else condition
            if (b)
                System.out.println(" both are equal");
            else
                System.out.println(" both are not equal");
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```
ByteBuffer 1:  [20, 30, 40, 0, 0]
 ByteBuffer 2:  [20, 30, 40]
 both are not equal

```