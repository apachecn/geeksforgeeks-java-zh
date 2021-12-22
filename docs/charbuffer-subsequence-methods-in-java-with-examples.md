# Java 中的 CharBuffer subSequence()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-subsequer-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-subsequence-methods-in-java-with-examples/)

**[java.nio.CharBuffer 类](https://www.geeksforgeeks.org/tag/java-charbuffer/)** 的 **subSequence()** 方法用于创建一个新的字符缓冲区，该字符缓冲区表示该缓冲区相对于当前位置的指定子序列。

新缓冲区将共享该缓冲区的内容；也就是说，如果这个缓冲区的内容是可变的，那么对一个缓冲区的修改将导致另一个缓冲区被修改。新缓冲区的容量将是该缓冲区的容量，其位置将是位置()+开始，其限制将是位置()+结束。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```java
public abstract CharBuffer
    subSequence(int start, int end)
```

**参数:**此方法采用以下参数。

*   **start–**子序列中第一个字符相对于当前位置的索引；必须是非负的，并且不大于剩余的()。
*   **end–**子序列中最后一个字符之后的字符相对于当前位置的索引；必须不小于起始值，也不大于剩余值()。

**返回值:**该方法返回新的字符缓冲区。

**异常:**如果开始和结束的前提条件不成立，该方法抛出**indexout of boundsexception**。

以下是说明 SupRe()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// subSequence() method

import java.nio.*;
import java.util.*;
import java.io.IOException;

public class GFG {
    public static void main(String[] args)
    {
        try {

            // Declare and initialize the char array
            char[] cb = { 'a', 'b', 'c', 'd', 'e' };

            // wrap the char array into CharBuffer
            // using wrap() method
            CharBuffer charBuffer
                = CharBuffer.wrap(cb);

            // charBuffer.position(3);

            // Getting new CharBuffer
            // using subSequence() method
            CharBuffer cb2 = charBuffer.subSequence(2, 4);

            // print the byte buffer
            System.out.println("Original CharBuffer : "
                               + Arrays.toString(
                                     charBuffer.array())
                               + "\nPosition: "
                               + charBuffer.position()
                               + "\nLimit: "
                               + charBuffer.limit()
                               + "\n\nNew Charbuffer: "
                               + Arrays.toString(
                                     cb2.array())
                               + "\nPosition: "
                               + cb2.position()
                               + "\nLimit: "
                               + cb2.limit());
        }
        catch (IndexOutOfBoundsException e) {
            System.out.println("index is out of bound");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**输出:**

```java
Original CharBuffer : [a, b, c, d, e]
Position: 0
Limit: 5

New Charbuffer: [a, b, c, d, e]
Position: 2
Limit: 4

```

**示例 2:**For indexout of bound 异常

```java
// Java program to demonstrate
// subSequence() method

import java.nio.*;
import java.util.*;
import java.io.IOException;

public class GFG {
    public static void main(String[] args)
    {
        try {

            // Declare and initialize the char array
            char[] cb = { 'a', 'b', 'c', 'd', 'e' };

            // wrap the char array into CharBuffer
            // using wrap() method
            CharBuffer charBuffer
                = CharBuffer.wrap(cb);

            // charBuffer.position(3);

            // Getting new CharBuffer
            // using subSequence() method
            CharBuffer cb2
                = charBuffer.subSequence(-2, 4);

            // print the byte buffer
            System.out.println("Original CharBuffer : "
                               + Arrays.toString(
                                     charBuffer.array())
                               + "\nPosition: "
                               + charBuffer.position()
                               + "\nLimit: "
                               + charBuffer.limit()
                               + "\n\nNew Charbuffer: "
                               + Arrays.toString(
                                     cb2.array())
                               + "\nPosition: "
                               + cb2.position()
                               + "\nLimit: "
                               + cb2.limit());
        }
        catch (IndexOutOfBoundsException e) {
            System.out.println("index is out of bound");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

T5】输出:

```java
index is out of bound
Exception throws: java.lang.IndexOutOfBoundsException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charbuffer . html # subsequel-int-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#subSequence-int-int-)