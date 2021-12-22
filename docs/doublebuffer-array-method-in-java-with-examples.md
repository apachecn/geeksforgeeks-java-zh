# Java 中的 DoubleBuffer 数组()方法示例

> 原文:[https://www . geesforgeks . org/double buffer-array-in-Java-method-with-examples/](https://www.geeksforgeeks.org/doublebuffer-array-method-in-java-with-examples/)

**java.nio.DoubleBuffer** 类的**数组()**方法用于返回支持该缓冲区的双数组。对此缓冲区内容的修改将导致返回数组的内容被修改，反之亦然。Invoke()在调用此方法之前使用 hasArray()方法，以确保此缓冲区具有可访问的后备数组

**语法:**

```java
public final float[] array()

```

**返回值:**这个方法返回**支持这个缓冲区的数组。**

**异常:**如果此缓冲区由数组支持但为只读，则此方法将引发**readonlybufferrexception**。

下面的程序说明了 array()方法:

**实施例 1:**

```java
// Java program to demonstrate
// array() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 10;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            db.put(8.56F);
            db.put(2, 9.61F);
            db.rewind();

            // getting array from db DoubleBuffer using array() method
            double[] dbb = db.array();

            // printing the DoubleBuffer db
            System.out.println("DoubleBuffer:  "
                               + Arrays.toString(dbb));
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
DoubleBuffer:  [8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

```

**例 2:**

```java
// Java program to demonstrate
// array() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
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
            db.put(9.56F);
            db.put(2, 7.61F);
            db.put(3, 4.61F);
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
            db1.put(1, 4.56F);
            db1.put(2, 6.45F);
            db1.rewind();

            // print the DoubleBuffer
            System.out.println("\nDoubleBuffer db1:  "
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
DoubleBuffer db: [9.5600004196167, 0.0, 7.610000133514404, 4.610000133514404, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

DoubleBuffer db1:  [0.0, 4.559999942779541, 6.449999809265137, 0.0, 0.0]

ReadOnlyBuffer DoubleBuffer: 9.5600004196167, 0.0, 7.610000133514404, 4.610000133514404, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 

Trying to get the array from ReadOnlyDb for editing
Exception thrown: java.nio.ReadOnlyBufferException

```