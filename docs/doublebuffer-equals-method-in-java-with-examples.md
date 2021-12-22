# Java 中的 DoubleBuffer equals()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-equals-method-in-java-with-examples/)

**java.nio.DoubleBuffe** r 类的 **equals()** 方法用于检查给定的缓冲区是否等于另一个对象。

当且仅当两个双缓冲区相等时，

*   它们具有相同的元素类型，
*   它们具有相同数量的剩余元素，并且
*   剩余元素的两个序列，独立于它们的起始位置，是逐点相等的
    。

如果(a = = b)| |(double . isnan(a)& & double . isnan(b))，此方法认为两个双元素 a 和 b 相等。与 Double.equals(对象)不同，值-0.0 和+0.0 被认为是相等的。

双缓冲区不等于任何其他类型的对象。

**语法:**

```java
public boolean equals(Object ob)

```

**参数:**该方法将该缓冲区要与之比较的对象 **ob** 作为参数。

**返回值:**当且仅当该缓冲区等于给定对象时，该方法返回**真**。

下面是一些示例来说明 equals()方法:

**例 1:**

```java
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the  DoubleBuffer 2
        int capacity2 = 10;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer 1
            // and allocating size capacity
            DoubleBuffer db1 = DoubleBuffer.allocate(capacity1);

            // creating object of Doublebuffer 2
            // and allocating size capacity
            DoubleBuffer db2 = DoubleBuffer.allocate(capacity2);

            // putting the value in Doublebuffer 1
            db1.put(8.56F);
            db1.put(2, 9.61F);
            db1.rewind();

            // putting the value in Doublebuffer 2
            db2.put(8.56F);
            db2.put(2, 9.61F);
            db2.rewind();

            // print the DoubleBuffer 1
            System.out.println(" DoubleBuffer 1:  "
                               + Arrays.toString(db1.array()));

            // print the DoubleBuffer 2
            System.out.println(" DoubleBuffer 2:  "
                               + Arrays.toString(db2.array()));

            // checking the equality of both DoubleBuffer
            boolean dbb = db1.equals(db2);

            // checking if else condition
            if (dbb)
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
DoubleBuffer 1:  [8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
 DoubleBuffer 2:  [8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
both are equal

```

例 1:

```java
// Java program to demonstrate
// equals() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the  DoubleBuffer 2
        int capacity2 = 5;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer 1
            // and allocating size capacity
            DoubleBuffer db1 = DoubleBuffer.allocate(capacity1);

            // creating object of Doublebuffer 2
            // and allocating size capacity
            DoubleBuffer db2 = DoubleBuffer.allocate(capacity2);

            // putting the value in Doublebuffer 1
            db1.put(8.56F);
            db1.put(2, 9.61F);
            db1.rewind();

            // putting the value in Doublebuffer 2
            db2.put(8.56F);
            db2.put(2, 9.61F);
            db2.rewind();

            // print the DoubleBuffer 1
            System.out.println(" DoubleBuffer 1:  "
                               + Arrays.toString(db1.array()));

            // print the DoubleBuffer 2
            System.out.println(" DoubleBuffer 2:  "
                               + Arrays.toString(db2.array()));

            // checking the equality of both DoubleBuffer
            boolean dbb = db1.equals(db2);

            // checking if else condition
            if (dbb)
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
DoubleBuffer 1:  [8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
 DoubleBuffer 2:  [8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0]
both are not equal

```