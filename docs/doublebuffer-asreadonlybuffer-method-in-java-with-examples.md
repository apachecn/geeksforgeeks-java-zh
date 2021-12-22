# Java 中的 DoubleBuffer asReadOnlyBuffer()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-as readonly buffer-in-Java-method-with-examples/](https://www.geeksforgeeks.org/doublebuffer-asreadonlybuffer-method-in-java-with-examples/)

类的 **asReadOnlyBuffer()** 方法用于用这个缓冲区的内容创建一个新的只读双缓冲区。新缓冲区是该缓冲区的副本。因此，对此缓冲区内容所做的更改将在新缓冲区中可见。

由于新缓冲区是只读的，因此不允许对其内容进行任何修改。两个缓冲器的位置、极限和标记值将是独立的。新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。如果此缓冲区本身是只读的，则此方法的行为方式与复制方法完全相同。

**语法:**

```java
public abstract DoubleBuffer asReadOnlyBuffer()

```

**返回值:**该方法返回**新的只读双缓冲区**，内容与该缓冲区相同。

下面是说明 asReadOnlyBuffer()方法的示例:

**例 1:**

```java
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 10;

        // Creating the DoubleBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.allocate(capacity);

            // putting the value in floatbuffer
            db.put(8.56);
            db.put(2, 9.61);
            db.rewind();

            // print the DoubleBuffer
            System.out.println("Original DoubleBuffer: "
                               + Arrays.toString(db.array()));

            // Creating a read-only copy of DoubleBuffer
            // using asReadOnlyBuffer() method
            DoubleBuffer floatBuffer = db.asReadOnlyBuffer();

            // print the DoubleBuffer
            System.out.print("\nReadOnlyBuffer DoubleBuffer: ");

            while (floatBuffer.hasRemaining())
                System.out.print(floatBuffer.get() + ", ");
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
Original DoubleBuffer: [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

ReadOnlyBuffer DoubleBuffer: 8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0,

```

**例 2:**

```java
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args) throws Exception
    {

        // Declaring the capacity of the db
        int capacity1 = 10;

        // Declaring the capacity of the db1
        int capacity2 = 5;

        // Creating the DoubleBuffer
        try {

            //
            // db
            //
            // creating object of Doublebuffer db
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.allocate(capacity1);

            // putting the value in db
            db.put(8.56);
            db.put(2, 9.61);
            db.rewind();

            // print the DoubleBuffer
            System.out.println("DoubleBuffer db: "
                               + Arrays.toString(db.array()));

            //
            // db1
            //
            // creating object of Doublebuffer db1
            // and allocating size capacity
            DoubleBuffer db1 = DoubleBuffer.allocate(capacity2);

            // putting the value in db1
            db1.put(1, 4.56);
            db1.put(2, 6.45);
            db1.rewind();

            // print the DoubleBuffer
            System.out.println("\nDoubleBuffer db1: "
                               + Arrays.toString(db1.array()));

            // Creating a read-only copy of DoubleBuffer
            // using asReadOnlyBuffer() method
            DoubleBuffer readOnlyDb = db.asReadOnlyBuffer();

            // print the DoubleBuffer
            System.out.print("\nReadOnlyBuffer DoubleBuffer: ");

            while (readOnlyDb.hasRemaining())
                System.out.print(readOnlyDb.get() + ", ");

            // try to change readOnlyDb
            System.out.println("\n\nTrying to get the array"
                               + " from ReadOnlyDb for editing");
            Arrays.toString(readOnlyDb.array());
        }
        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }
        catch (ReadOnlyBufferException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
DoubleBuffer db: [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

DoubleBuffer db1: [0.0, 4.56, 6.45, 0.0, 0.0]

ReadOnlyBuffer DoubleBuffer: 8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 

Trying to get the array from ReadOnlyDb for editing
Exception thrown: java.nio.ReadOnlyBufferException

```