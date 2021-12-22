# Java 中的 CharBuffer charAt()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-charat-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-charat-methods-in-java-with-examples/)

**[Java . nio . charbuffer](https://www.geeksforgeeks.org/tag/java-charbuffer/)**类的 **charAt()** 方法用于读取相对于当前位置的给定索引处的字符。

**语法:**

```java
public final char charAt(int index)
```

**参数:**该方法取待读字符相对于位置的索引；必须是非负的，并且小于剩余的()。

**返回值:**该方法返回索引位置()+索引处的字符。

**异常:**如果索引上的前提条件不成立，该方法抛出**indexout of boundsexception**。

下面是说明 charAt(int index)方法的例子:

**例 1:**

```java
// Java program to demonstrate
// charAt() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Creating the CharBuffer
        try {

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
                                     charbuffer.array()));

            // Read char at particular Index
            // using charAt() method
            char value = charbuffer.charAt(2);

            // Display the value
            System.out.println("\nvalue at Index 0 is : "
                               + value);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is greater than"
                               + " the capacity minus 1");
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**输出:**

```java
Original CharBuffer:  [a, b, c]

value at Index 0 is : c

```

**示例 2:** 演示 IndexOutOfBoundsException。

```java
// Java program to demonstrate
// charAt() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // Creating the CharBuffer
        try {

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
                                     charbuffer.array()));

            // Read char at particular Index
            // using charAt() method
            char value = charbuffer.charAt(3);

            // Display the value
            System.out.println("\nvalue at Index 0 is : "
                               + value);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is greater than"
                               + " the capacity minus 1");
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**输出:**

```java
Original CharBuffer:  [a, b, c]

index is greater than the capacity minus 1
Exception throws : java.lang.IndexOutOfBoundsException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charbuffer . html # charAt-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#charAt-int-)