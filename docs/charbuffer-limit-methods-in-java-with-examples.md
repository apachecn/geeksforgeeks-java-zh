# Java 中的 CharBuffer limit()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-limit-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-limit-methods-in-java-with-examples/)

[java.nio.CharBuffer 类](https://www.geeksforgeeks.org/tag/java-charbuffer/)的**限制()**方法用于设置该缓冲区的限制。如果该位置大于新限制，则将其设置为新限制。如果标记已定义并且大于新的限制，则丢弃该标记。

**语法:**

```java
public CharBuffer limit(int newLimit)
```

**返回值:**这个方法返回这个缓冲区。

以下是举例说明 limit()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating CharBuffer
        // using allocate() method
        CharBuffer charBuffer = CharBuffer.allocate(4);

        // append char value in CharBuffer
        // using char() method
        charBuffer.append('a');
        charBuffer.append('b');

        // print the char buffer
        System.out.println("CharBuffer before "
                           + "setting buffer's limit: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());

        // Limit the CharBuffer
        // using limit() method
        charBuffer.limit(1);

        // print the char buffer
        System.out.println("CharBuffer before "
                           + "setting buffer's limit: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());
    }
}
```

**输出:**

```java
CharBuffer before setting buffer's limit: [a, b,,  ]
Position: 2
Limit: 4

CharBuffer after setting buffer's limit: [a, b,,  ]
Position: 1
Limit: 1

```

**示例 2:**

```java
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating CharBuffer
        // using allocate() method
        CharBuffer charBuffer
            = CharBuffer.allocate(5);

        // append char value in CharBuffer
        // using char() method
        charBuffer.append('a');
        charBuffer.append('b');
        charBuffer.append('c');

        // mark will be going to discarded by limit()
        charBuffer.mark();

        // print the char buffer
        System.out.println("CharBuffer before "
                           + "setting buffer's limit: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());

        // Limit the charBuffer
        // using limit() method
        charBuffer.limit(4);

        // print the char buffer
        System.out.println("CharBuffer before "
                           + "setting buffer's limit: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());
    }
}
```

**输出:**

```java
CharBuffer before setting buffer's limit: [a, b, c,,  ]
Position: 3
Limit: 5

CharBuffer after setting buffer's limit: [a, b, c,,  ]
Position: 3
Limit: 4

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charbuffer . html # limit-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#limit-int-)