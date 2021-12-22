# Java 中的 CharBuffer equals()方法

> 原文:[https://www . geesforgeks . org/char buffer-equals-method-in-Java/](https://www.geeksforgeeks.org/charbuffer-equals-method-in-java/)

**java.nio.CharBuffer** 类的 **equals()** 方法用于检查给定的缓冲区是否等于另一个对象。

当且仅当两个字符缓冲区相等时，

*   它们具有相同的元素类型，
*   它们具有相同数量的剩余元素，并且
*   剩余元素的两个序列，独立于它们的起始位置，是逐点相等的
    。

如果(' a ' = ' b ')| |(char . isnan(a)和& Char.isNaN(b))，此方法认为两个字符元素' a '和' b '相等。与 Char.equals(对象)不同，值-0 和+0 被认为是相等的。

字符缓冲区不等于任何其他类型的对象。

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

        // Declaring the capacity of the CharBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the CharBuffer 2
        int capacity2 = 10;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer 1
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity1);

            // creating object of Charbuffer 2
            // and allocating size capacity
            CharBuffer cb2 = CharBuffer.allocate(capacity2);

            // putting the value in Charbuffer 1
            cb1.put('a');
            cb1.put(2, 'b');
            cb1.rewind();

            // putting the value in Charbuffer 2
            cb2.put('a');
            cb2.put(2, 'b');
            cb2.rewind();

            // print the CharBuffer 1
            System.out.println(" CharBuffer 1: "
                               + Arrays.toString(cb1.array()));

            // print the CharBuffer 2
            System.out.println(" CharBuffer 2: "
                               + Arrays.toString(cb2.array()));

            // checking the equality of both CharBuffer
            boolean cbb = cb1.equals(cb2);

            // checking if else condition
            if (cbb)
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

```java
CharBuffer 1: [a,, b,,,,,,, ]
 CharBuffer 2: [a,, b,,,,,,, ]
Both are equal

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

        // Declaring the capacity of the CharBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the CharBuffer 2
        int capacity2 = 5;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer 1
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity1);

            // creating object of Charbuffer 2
            // and allocating size capacity
            CharBuffer cb2 = CharBuffer.allocate(capacity2);

            // putting the value in Charbuffer 1
            cb1.put('a');
            cb1.put(2, 'b');
            cb1.rewind();

            // putting the value in Charbuffer 2
            cb2.put('a');
            cb2.put(2, 'b');
            cb2.rewind();

            // print the CharBuffer 1
            System.out.println(" CharBuffer 1: "
                               + Arrays.toString(cb1.array()));

            // print the CharBuffer 2
            System.out.println(" CharBuffer 2: "
                               + Arrays.toString(cb2.array()));

            // checking the equality of both CharBuffer
            boolean cbb = cb1.equals(cb2);

            // checking if else condition
            if (cbb)
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

```java
CharBuffer 1: [a,, b,,,,,,, ]
 CharBuffer 2: [a,, b,, ]
Both are not equal

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

        // Declaring the capacity of the CharBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the CharBuffer 2
        int capacity2 = 10;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer 1
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity1);

            // creating object of Charbuffer 2
            // and allocating size capacity
            CharBuffer cb2 = CharBuffer.allocate(capacity2);

            // putting the value in Charbuffer 1
            cb1.put('a');
            cb1.put(2, 'b');
            cb1.rewind();

            // putting the value in Charbuffer 2
            cb2.put('a');
            cb2.put(2, 'b');
            cb2.put(3, 'c');
            cb2.put(4, 'd');
            cb2.rewind();

            // print the CharBuffer 1
            System.out.println(" CharBuffer 1: "
                               + Arrays.toString(cb1.array()));

            // print the CharBuffer 2
            System.out.println(" CharBuffer 2: "
                               + Arrays.toString(cb2.array()));

            // checking the equality of both CharBuffer
            boolean cbb = cb1.equals(cb2);

            // checking if else condition
            if (cbb)
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

```java
CharBuffer 1: [a,, b,,,,,,, ]
 CharBuffer 2: [a,, b, c, d,,,,, ]
Both are not equal

```