# Java 中的 CharBuffer compareTo()方法

> 原文:[https://www . geesforgeks . org/char buffer-compare to-method-in-Java/](https://www.geeksforgeeks.org/charbuffer-compareto-method-in-java/)

**java.nio.charBuffer** 类的 **compareTo()** 方法用于比较一个缓冲区和另一个缓冲区。两个字符缓冲区是通过按字典顺序比较剩余元素的序列来进行比较的，而不考虑每个序列在其相应缓冲区内的起始位置。像调用 Char.compare(char，char)一样对成对的字符元素进行比较。任何其他类型的对象都不能与 char buffer 相比。

**语法:**

```java
public int compareTo(CharBuffer that)
```

**参数:**该方法将一个 **charbuffer 对象**作为参数，与该缓冲区进行比较。

**返回值:**该方法返回一个**负整数、零或一个正整数**，因为该缓冲区小于、等于或大于给定的缓冲区。

下面是说明 compareTo()方法的示例:

**例 1:** 当两个 CharBuffer 相等时。

```java
// Java program to demonstrate
// compareTo() method
import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the cb
        int capacity1 = 3;

        // Creating the CharBuffer
        try {

            // creating object of charbuffer cb
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity1);

            // putting the value in cb
            cb.put('a');
            cb.put('b');
            cb.put('c');

            // revind the float buffer
            cb.rewind();

            // print the Charbuffer
            System.out.println("Charbuffer cb: "
                               + Arrays.toString(cb.array()));

            // creating object of floatbuffer cb1
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity1);

            // putting the value in cb1
            cb1.put('a');
            cb1.put('b');
            cb1.put('c');

            // revind the float buffer
            cb1.rewind();

            // print the Charbuffer
            System.out.println("Charbuffer cb1: "
                               + Arrays.toString(cb1.array()));

            // compare both buffer and store the value into integer
            int i = cb.compareTo(cb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are"
                                   + "lexicographically equal");

            else if (i >= 0)
                System.out.println("\ncb is lexicographically"
                                   + "greater than cb1");

            else
                System.out.println("\ncb is lexicographically"
                                   + "less than cb1");
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
Charbuffer cb: [a, b, c]
Charbuffer cb1: [a, b, c]

both buffer arelexicographically equal

```

**示例 2:** 当该浮动填充大于传递的浮动填充时

```java
// Java program to demonstrate
// compareTo() method
import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the cb
        int capacity1 = 3;

        // Creating the CharBuffer
        try {

            // creating object of floatbuffer cb
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity1);

            // putting the value in cb
            cb.put('g');
            cb.put('b');
            cb.put('c');

            // revind the float buffer
            cb.rewind();

            // print the CharBuffer
            System.out.println("CharBuffer cb: "
                               + Arrays.toString(cb.array()));

            // creating object of floatbuffer cb1
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity1);

            // putting the value in cb1
            cb1.put('a');
            cb1.put('b');
            cb1.put('c');

            // revind the float buffer
            cb1.rewind();

            // print the CharBuffer
            System.out.println("CharBuffer cb1: "
                               + Arrays.toString(cb1.array()));

            // compare both buffer and store
            // the value into integer
            int i = cb.compareTo(cb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are"
                                   + " lexicographically equal");

            else if (i >= 0)
                System.out.println("\ncb is lexicographically"
                                   + " greater than cb1");

            else
                System.out.println("\ncb is lexicographically"
                                   + " less than cb1");
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
CharBuffer cb: [g, b, c]
CharBuffer cb1: [a, b, c]

cb is lexicographically greater than cb1

```

**示例 3:** 当该浮动填充小于传递的浮动填充时

```java
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the cb
        int capacity1 = 3;

        // Creating the CharBuffer
        try {

            // creating object of CharBuffer cb
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity1);

            // putting the value in cb
            cb.put('a');
            cb.put('b');
            cb.put('c');

            // revind the float buffer
            cb.rewind();

            // print the CharBuffer
            System.out.println("CharBuffer cb: "
                               + Arrays.toString(cb.array()));

            // creating object of CharBuffer cb1
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity1);

            // putting the value in cb1
            cb1.put('g');
            cb1.put('b');
            cb1.put('c');

            // revind the float buffer
            cb1.rewind();

            // print the CharBuffer
            System.out.println("CharBuffer cb1: "
                               + Arrays.toString(cb1.array()));

            // compare both buffer and store the value into integer
            int i = cb.compareTo(cb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are"
                                   + "lexicographically equal");
            else if (i >= 0)
                System.out.println("\ncb is lexicographically"
                                   + "greater than cb1");
            else
                System.out.println("\ncb is lexicographically"
                                   + "less than cb1");
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
CharBuffer cb: [a, b, c]
CharBuffer cb1: [g, b, c]

cb is lexicographicallyless than cb1

```