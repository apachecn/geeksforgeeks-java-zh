# Java 中的 DoubleBuffer compareTo()方法，带示例

> 原文:[https://www . geesforgeks . org/double buffer-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-compareto-method-in-java-with-examples/)

**java.nio.DoubleBuffer** 类的 **compareTo()** 方法用于比较一个缓冲区和另一个缓冲区。两个双缓冲区通过按字典顺序比较剩余元素的序列来进行比较，而不考虑每个序列在其相应缓冲区内的起始位置。除了-0.0 和 0.0 被认为是相等的之外，对浮点元素的比较就像调用 Double.compare(Double，double)一样。双倍。通过这种方法，NaN 被认为等于它自己，并且大于所有其他双精度值(包括 double。正数 _ 无穷大)。双缓冲区无法与任何其他类型的对象相比。

**语法:**

```java
public int compareTo(DoubleBuffer that)
```

**参数:**该方法以一个**双缓冲区对象**作为参数，与该缓冲区进行比较。

**返回值:**该方法返回一个**负整数、零或一个正整数** r，因为该缓冲区小于、等于或大于给定的缓冲区。

下面是说明 compareTo()方法的示例:

**示例 1:** 当两个双缓冲区相等时。

```java
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the db
        int capacity1 = 3;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer db
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.allocate(capacity1);

            // putting the value in db
            db.put(9.56);
            db.put(7.61);
            db.put(4.61);

            // revind the Double buffer
            db.rewind();

            // print the DoubleBuffer
            System.out.println("DoubleBuffer db: "
                               + Arrays.toString(db.array()));

            // creating object of Doublebuffer db1
            // and allocating size capacity
            DoubleBuffer db1 = DoubleBuffer.allocate(capacity1);

            // putting the value in db1
            db1.put(9.56);
            db1.put(7.61);
            db1.put(4.61);

            // revind the Double buffer
            db1.rewind();

            // print the DoubleBuffer
            System.out.println("DoubleBuffer db1: "
                               + Arrays.toString(db1.array()));

            // compare both buffer and store the value into integer
            int i = db.compareTo(db1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\ndb is lexicographically greater than db1");
            else
                System.out.println("\ndb is lexicographically less than db1");
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:**

```java
DoubleBuffer db: [9.56, 7.61, 4.61]
DoubleBuffer db1: [9.56, 7.61, 4.61]

both buffer are lexicographically equal

```

**示例 2:** 当该双缓冲区大于传递的双缓冲区时

```java
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the db
        int capacity1 = 3;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer db
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.allocate(capacity1);

            // putting the value in db
            db.put(9.56);
            db.put(7.61);
            db.put(4.61);

            // revind the Double buffer
            db.rewind();

            // print the DoubleBuffer
            System.out.println("DoubleBuffer db: "
                               + Arrays.toString(db.array()));

            // creating object of Doublebuffer db1
            // and allocating size capacity
            DoubleBuffer db1 = DoubleBuffer.allocate(capacity1);

            // putting the value in db1
            db1.put(8.56);
            db1.put(7.61);
            db1.put(4.61);

            // revind the Double buffer
            db1.rewind();

            // print the DoubleBuffer
            System.out.println("DoubleBuffer db1: "
                               + Arrays.toString(db1.array()));

            // compare both buffer and store the value into integer
            int i = db.compareTo(db1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\ndb is lexicographically greater than db1");
            else
                System.out.println("\ndb is lexicographically less than db1");
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:**

```java
DoubleBuffer db: [9.56, 7.61, 4.61]
DoubleBuffer db1: [8.56, 7.61, 4.61]

db is lexicographically greater than db1

```