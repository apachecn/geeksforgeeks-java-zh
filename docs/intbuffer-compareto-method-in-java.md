# Java 中的 IntBuffer compareTo()方法

> 原文:[https://www . geesforgeks . org/int buffer-compare to-method-in-Java/](https://www.geeksforgeeks.org/intbuffer-compareto-method-in-java/)

**java.nio.IntBuffer** 类的 **compareTo()** 方法用于比较一个缓冲区和另一个缓冲区。两个 int 缓冲区通过字典式地比较它们剩余元素的序列来进行比较，而不考虑每个序列在其对应缓冲区内的起始位置。像调用 Int.compare(Int，int)一样比较 int 元素对，不同的是-0 和 0 被认为是相等的。里面的这个方法认为 NaN 等于它自己，并且大于所有其他 int 值(包括 Int。正数 _ 无穷大)。int 缓冲区无法与任何其他类型的对象相比较。

**语法:**

```
public int compareTo(IntBuffer that)
```

**参数**:该方法以一个 **intbuffer 对象**作为参数，与该缓冲区进行比较。

**返回值:**该方法返回一个**负整数、零或一个正整数**，因为该缓冲区小于、等于或大于给定的缓冲区。

下面的程序说明了 **compareTo()** 方法:

**示例 1:** 当两个 IntBuffer 相等时。

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ib
        int capacity1 = 3;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer ib
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity1);

            // putting the value in ib
            ib.put(9);
            ib.put(7);
            ib.put(4);

            // revind the Int buffer
            ib.rewind();

            // print the IntBuffer
            System.out.println("IntBuffer ib: "
                               + Arrays.toString(ib.array()));

            // creating object of Intbuffer ib1
            // and allocating size capacity
            IntBuffer ib1 = IntBuffer.allocate(capacity1);

            // putting the value in ib1
            ib1.put(9);
            ib1.put(7);
            ib1.put(4);

            // revind the Int buffer
            ib1.rewind();

            // print the IntBuffer
            System.out.println("IntBuffer ib1: "
                               + Arrays.toString(ib1.array()));

            // compare both buffer and store the value into integer
            int i = ib.compareTo(ib1);

            // if else condition
            if (i == 0)
                System.out.println("\nBoth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\nib is lexicographically greater than ib1");
            else
                System.out.println("\nib is lexicographically less than ib1");
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

```
IntBuffer ib: [9, 7, 4]
IntBuffer ib1: [9, 7, 4]

Both buffer are lexicographically equal

```

**示例 2:** 当该输入缓冲区大于传递的输入缓冲区时

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ib
        int capacity1 = 3;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer ib
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity1);

            // putting the value in ib
            ib.put(9);
            ib.put(7);
            ib.put(4);

            // revind the Int buffer
            ib.rewind();

            // print the IntBuffer
            System.out.println("IntBuffer ib: "
                               + Arrays.toString(ib.array()));

            // creating object of Intbuffer ib1
            // and allocating size capacity
            IntBuffer ib1 = IntBuffer.allocate(capacity1);

            // putting the value in ib1
            ib1.put(8);
            ib1.put(7);
            ib1.put(4);

            // revind the Int buffer
            ib1.rewind();

            // print the IntBuffer
            System.out.println("IntBuffer ib1: "
                               + Arrays.toString(ib1.array()));

            // compare both buffer and store the value into integer
            int i = ib.compareTo(ib1);

            // if else condition
            if (i == 0)
                System.out.println("\nBoth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\nib is lexicographically greater than ib1");
            else
                System.out.println("\nib is lexicographically less than ib1");
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

```
IntBuffer ib: [9, 7, 4]
IntBuffer ib1: [8, 7, 4]

ib is lexicographically greater than ib1

```

**例 3:** 当这个 IntBuffer 小于传递的 IntBuffer 时。

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ib
        int capacity1 = 3;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer ib
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity1);

            // putting the value in ib
            ib.put(8);
            ib.put(7);
            ib.put(4);

            // revind the Int buffer
            ib.rewind();

            // print the IntBuffer
            System.out.println("IntBuffer ib: "
                               + Arrays.toString(ib.array()));

            // creating object of Intbuffer ib1
            // and allocating size capacity
            IntBuffer ib1 = IntBuffer.allocate(capacity1);

            // putting the value in ib1
            ib1.put(9);
            ib1.put(7);
            ib1.put(4);

            // revind the Int buffer
            ib1.rewind();

            // print the IntBuffer
            System.out.println("IntBuffer ib1: "
                               + Arrays.toString(ib1.array()));

            // compare both buffer and store the value into integer
            int i = ib.compareTo(ib1);

            // if else condition
            if (i == 0)
                System.out.println("\nBoth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\nib is lexicographically greater than ib1");
            else
                System.out.println("\nib is lexicographically less than ib1");
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

```
IntBuffer ib: [8, 7, 4]
IntBuffer ib1: [9, 7, 4]

ib is lexicographically less than ib1

```