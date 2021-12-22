# Java 中的 DoubleBuffer compact()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-compact-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-compact-method-in-java-with-examples/)

**java.nio.DoubleBuffer** 类的 **compact()** 方法用于压缩给定的缓冲区。

缓冲区的当前位置与其限制之间的值被复制到缓冲区的开头。然后，缓冲器的位置被设置为 n+1，其极限被设置为其容量。缓冲区的位置被设置为复制的浮点数。

**语法:**

```java
public abstract DoubleBuffer compact()
```

**返回值:**该方法返回与该缓冲区内容相同的**新双缓冲区**。

**异常:**如果这个缓冲区是只读的，这个方法抛出**readonlybufferrexception**。

下面的程序说明了 compact()方法:

**实施例 1:**

```java
// Java program to demonstrate
// compact() method

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
        db.put(9.61F);
        db.put(9.61F);

        // print the DoubleBuffer
        System.out.println("Original DoubleBuffer: "
                           + Arrays.toString(db.array()));

        System.out.println("Position: " + db.position());

        System.out.println("limit: " + db.limit());

        // Creating a compacted  DoubleBuffer of same DoubleBuffer
        // using compact() method
        DoubleBuffer DoubleBuffer = db.compact();

        // print the DoubleBuffer
        System.out.println("\nCompacted DoubleBuffer: "
                           + Arrays.toString(DoubleBuffer.array()));

        System.out.println("Position: " + DoubleBuffer.position());

        System.out.println("limit: " + DoubleBuffer.limit());

        // putting the value in compacted Doublebuffer
        DoubleBuffer.put(9.61F);

        // print the DoubleBuffer
        System.out.println("\nUpdated Compacted DoubleBuffer: "
                           + Arrays.toString(DoubleBuffer.array()));
        System.out.println("Position: " + DoubleBuffer.position());
        System.out.println("limit: " + DoubleBuffer.limit());
    }
}
```

**Output:**

```java
Original DoubleBuffer: [8.5600004196167, 9.609999656677246, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
Position: 3
limit: 10

Compacted DoubleBuffer: [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
Position: 7
limit: 10

Updated Compacted DoubleBuffer: [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 9.609999656677246, 0.0, 0.0]
Position: 8
limit: 10

```

**示例 2:** 显示 ReadOnlyBufferException

```java
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 10;

        // Creating the DoubleBuffer
        try {

            // creating object of DoubleBuffer
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            db.put(8.56F);
            db.put(9.61F);
            db.put(9.61F);
            db.rewind();

            // Creating a read-only copy of DoubleBuffer
            // using asReadOnlyBuffer() method
            DoubleBuffer db1 = db.asReadOnlyBuffer();

            // print the ReadOnlyBuffer
            System.out.print("ReadOnlyBuffer DoubleBuffer: ");
            while (db1.hasRemaining())
                System.out.print(db1.get() + ", ");
            System.out.println("");

            // print the Position of DoubleBuffer db
            System.out.println("\nPosition: " + db.position());

            // print the Limit of DoubleBuffer db
            System.out.println("\nlimit: " + db.limit());

            // Creating a compacted  DoubleBuffer of same ReadOnlyBuffer
            // using compact() method
            System.out.println("\nTrying to compact the ReadOnlyBuffer db1");
            DoubleBuffer DoubleBuffer = db1.compact();
        }

        catch (IllegalArgumentException e) {

            System.out.println("Exception throws " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws " + e);
        }
    }
}
```

**Output:**

```java
ReadOnlyBuffer DoubleBuffer: 8.5600004196167, 9.609999656677246, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 

Position: 0

limit: 10

Trying to compact the ReadOnlyBuffer db1
Exception throws java.nio.ReadOnlyBufferException

```