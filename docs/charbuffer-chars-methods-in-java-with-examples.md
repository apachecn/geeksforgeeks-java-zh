# Java 中的 CharBuffer chars()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-chars-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-chars-methods-in-java-with-examples/)

**[Java . nio . charbuffer](https://www.geeksforgeeks.org/tag/java-charbuffer/)**类的 **chars()** 方法用于返回一个 int 零扩展流，从这个序列中扩展 char 值。任何映射到代理代码点的字符都是通过未解释的。当终端流操作开始时，[流](https://www.geeksforgeeks.org/stream-in-java/)绑定到该序列(具体来说，对于可变序列，流的[分裂器](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/)是[后期绑定](https://www.geeksforgeeks.org/difference-between-early-and-late-binding-in-java/))。如果在操作过程中修改了序列，那么结果是未定义的。

**语法:**

```java
public IntStream chars()
```

**返回值:**这个方法从这个序列中返回一个字符值的**输入流**。

以下是说明 chars()方法的示例:

**例 1:**

```java
// Java program to demonstrate
// chars() method

import java.nio.*;
import java.util.*;
import java.util.stream.IntStream;

public class GFG {
    public static void main(String[] args)
    {
        // creating object of CharBuffer
        // and allocating size capacity
        CharBuffer charbuffer
            = CharBuffer.allocate(3);

        // append the value in CharBuffer
        // using append() method
        charbuffer.append('a')
            .append('b')
            .append('c')
            .rewind();

        // print the CharBuffer
        System.out.println("Original CharBuffer:  "
                           + Arrays.toString(
                                 charbuffer.array())
                           + "\n");

        // Read char at particular Index
        // using charAt() method
        IntStream stream = charbuffer.chars();

        // Display the stream of int zero-extending
        // the char values from this sequence
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```java
Original CharBuffer:  [a, b, c]

97
98
99

```

**例 2:**

```java
// Java program to demonstrate
// chars() method

import java.nio.*;
import java.util.*;
import java.util.stream.IntStream;

public class GFG {
    public static void main(String[] args)
    {
        // creating object of CharBuffer
        // and allocating size capacity
        CharBuffer charbuffer
            = CharBuffer.allocate(5);

        // append the value in CharBuffer
        // using append() method
        charbuffer.append((char)140)
            .append((char)117)
            .append((char)118)
            .append((char)0)
            .append((char)90)
            .rewind();

        // print the CharBuffer
        System.out.println("Original CharBuffer:  "
                           + Arrays.toString(
                                 charbuffer.array())
                           + "\n");

        // Read char at particular Index
        // using charAt() method
        IntStream stream = charbuffer.chars();

        // Display the stream of int zero-extending
        // the char values from this sequence
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```java
Original CharBuffer:  [?, u, v,  , Z]

140
117
118
0
90

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/nio/charbuffer . html # chars--](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#chars--)