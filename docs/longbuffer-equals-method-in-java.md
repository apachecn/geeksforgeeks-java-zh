# Java 中的 LongBuffer equals()方法

> 原文:[https://www . geesforgeks . org/longbuffer-equals-method-in-Java/](https://www.geeksforgeeks.org/longbuffer-equals-method-in-java/)

**java.nio.LongBuffer** 类的 **equals()** 方法用于检查给定的缓冲区是否等于另一个对象。

两个长缓冲区相等当且仅当，

*   它们具有相同的元素类型，
*   它们具有相同数量的剩余元素，并且
*   剩余元素的两个序列，无论它们的起始位置如何，都是相等的。

如果(a == b) || (Long.isNaN(a)和& Long.isNaN(b))，此方法认为两个 Long 元素 a 和 b 相等。与 Long.equals(对象)不同，值-0 和+0 被认为是相等的。

长缓冲区不等于任何其他类型的对象。

**语法:**

```
public boolean equals(Object ob)
```

**参数:**该方法以 **ob** (该缓冲区要与之比较的对象)为参数。

**返回值:**当且仅当该缓冲区等于给定对象时，该方法返回**真**。

以下是说明**等于()**方法的示例:

**实施例 1:**

```
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the  LongBuffer 2
        int capacity2 = 10;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer 1
            // and allocating size capacity
            LongBuffer ib1 = LongBuffer.allocate(capacity1);

            // creating object of Longbuffer 2
            // and allocating size capacity
            LongBuffer ib2 = LongBuffer.allocate(capacity2);

            // putting the value in Longbuffer 1
            ib1.put(8);
            ib1.put(2, 9);
            ib1.rewind();

            // putting the value in Longbuffer 2
            ib2.put(8);
            ib2.put(2, 9);
            ib2.rewind();

            // prLong the LongBuffer 1
            System.out.println(" LongBuffer 1:  "
                               + Arrays.toString(ib1.array()));

            // prLong the LongBuffer 2
            System.out.println(" LongBuffer 2:  "
                               + Arrays.toString(ib2.array()));

            // checking the equality of both LongBuffer
            boolean ibb = ib1.equals(ib2);

            // checking if else condition
            if (ibb)
                System.out.println("Both are equal");
            else
                System.out.println("Both are not equal");
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

```
LongBuffer 1:  [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]
LongBuffer 2:  [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]
Both are equal

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

        // Declaring the capacity of the LongBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the  LongBuffer 2
        int capacity2 = 5;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer 1
            // and allocating size capacity
            LongBuffer ib1 = LongBuffer.allocate(capacity1);

            // creating object of Longbuffer 2
            // and allocating size capacity
            LongBuffer ib2 = LongBuffer.allocate(capacity2);

            // putting the value in Longbuffer 1
            ib1.put(8);
            ib1.put(2, 9);
            ib1.rewind();

            // putting the value in Longbuffer 2
            ib2.put(8);
            ib2.put(2, 9);
            ib2.rewind();

            // prLong the LongBuffer 1
            System.out.println(" LongBuffer 1:  "
                               + Arrays.toString(ib1.array()));

            // prLong the LongBuffer 2
            System.out.println(" LongBuffer 2:  "
                               + Arrays.toString(ib2.array()));

            // checking the equality of both LongBuffer
            boolean ibb = ib1.equals(ib2);

            // checking if else condition
            if (ibb)
                System.out.println("Both are equal");
            else
                System.out.println("Both are not equal");
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

```
LongBuffer 1:  [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]
LongBuffer 2:  [8, 0, 9, 0, 0]
Both are not equal

```

**实施例 3:**

```
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the  LongBuffer 2
        int capacity2 = 10;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer 1
            // and allocating size capacity
            LongBuffer ib1 = LongBuffer.allocate(capacity1);

            // creating object of Longbuffer 2
            // and allocating size capacity
            LongBuffer ib2 = LongBuffer.allocate(capacity2);

            // putting the value in Longbuffer 1
            ib1.put(8);
            ib1.put(2, 9);
            ib1.rewind();

            // putting the value in Longbuffer 2
            ib2.put(8);
            ib2.put(2, 9);
            ib2.put(3, 7);
            ib2.put(4, 4);
            ib2.rewind();

            // prLong the LongBuffer 1
            System.out.println(" LongBuffer 1:  "
                               + Arrays.toString(ib1.array()));

            // prLong the LongBuffer 2
            System.out.println(" LongBuffer 2:  "
                               + Arrays.toString(ib2.array()));

            // checking the equality of both LongBuffer
            boolean ibb = ib1.equals(ib2);

            // checking if else condition
            if (ibb)
                System.out.println("Both are equal");
            else
                System.out.println("Both are not equal");
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

```
LongBuffer 1:  [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]
LongBuffer 2:  [8, 0, 9, 7, 4, 0, 0, 0, 0, 0]
Both are not equal

```