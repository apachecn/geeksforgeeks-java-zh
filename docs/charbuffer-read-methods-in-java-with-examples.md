# Java 中的 CharBuffer read()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-read-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-read-methods-in-java-with-examples/)

**java.nio.CharBuffer 类**的 **read()** 方法用于将字符读入指定的字符缓冲区。缓冲区按原样用作字符存储库:所做的唯一更改是 put 操作的结果。不执行缓冲区的翻转或倒回。

**语法:**

```
public int read(CharBuffer target)
```

**参数:**该方法取读取字符的缓冲区。

**返回值:**这个方法返回添加到缓冲区的字符数，如果这个字符源在它的末尾，则返回-1。

**异常:**该方法抛出以下异常:-

*   **ioexception** –If there is an I/O error
*   null 指针异常你好
*   **readonlybufferception** -If the destination is a read-only buffer

下面是举例说明 read()方法的例子:

**示例 1:**

```
// Java program to demonstrate
// read() method

import java.nio.*;
import java.util.*;
import java.io.IOException;

public class GFG {
    public static void main(String[] args)
    {
        try {

            // Declare and initialize the char array
            char[] cb1 = { 'x', 'y', 'z' };
            char[] cb2 = { 'a', 'b', 'c', 'd', 'e' };

            // wrap the char array into CharBuffer
            // using wrap() method
            CharBuffer charBuffer1
                = CharBuffer.wrap(cb1);

            // wrap the char array into CharBuffer
            // using wrap() method
            CharBuffer charBuffer2
                = CharBuffer.wrap(cb2);

            // print the byte buffer
            System.out.println("CharBuffer Before operation is: "
                               + Arrays.toString(
                                     charBuffer1.array())
                               + "\nTarget Charbuffer: "
                               + Arrays.toString(
                                     charBuffer2.array()));

            // Get the value of the number of Character
            // read from the charBuffer
            // using read() method
            int value
                = charBuffer1
                      .read(charBuffer2);

            // print the byte buffer
            System.out.println("\nCharBuffer After operation is: "
                               + Arrays.toString(
                                     charBuffer1.array())
                               + "\nTarget Charbuffer: "
                               + Arrays.toString(
                                     charBuffer2.array())
                               + "\nno of value changed: "
                               + value);
        }
        catch (IOException e) {
            System.out.println("an I/O error occurs");
            System.out.println("Exception throws: " + e);
        }
        catch (NullPointerException e) {
            System.out.println("target charbuffer is null");
            System.out.println("Exception throws: " + e);
        }
        catch (ReadOnlyBufferException e) {
            System.out.println("target is a read only buffer");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**输出:**

```
CharBuffer Before operation is: [x, y, z]
Target Charbuffer: [a, b, c, d, e]

CharBuffer After operation is: [x, y, z]
Target Charbuffer: [x, y, z, d, e]
no of value changed: 3

```

**示例 2:** 为空指针异常

```
// Java program to demonstrate
// read() method

import java.nio.*;
import java.util.*;
import java.io.IOException;

public class GFG {
    public static void main(String[] args)
    {
        try {

            // Declare and initialize the char array
            char[] cb1 = { 'x', 'y', 'z' };

            // wrap the char array into CharBuffer
            // using wrap() method
            CharBuffer charBuffer1
                = CharBuffer.wrap(cb1);

            // print the byte buffer
            System.out.println("CharBuffer Before operation is: "
                               + Arrays.toString(
                                     charBuffer1.array()));

            // Get the value of number of Character
            // read from the charBuffer
            // using read() method
            int value = charBuffer1.read(null);
        }

        catch (IOException e) {
            System.out.println("\nan I/O error occurs");
            System.out.println("Exception throws: " + e);
        }

        catch (NullPointerException e) {
            System.out.println("\ntarget charbuffer is null");
            System.out.println("Exception throws: " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("\ntarget is a read only buffer");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

T5】输出:

```
CharBuffer Before operation is: [x, y, z]

target charbuffer is null
Exception throws: java.lang.NullPointerException

```

**例 3:** 为 readonly buffer exception

```
// Java program to demonstrate
// read() method

import java.nio.*;
import java.util.*;
import java.io.IOException;

public class GFG {
    public static void main(String[] args)
    {
        try {

            // Declare and initialize the char array
            char[] cb1 = { 'x', 'y', 'z' };
            char[] cb2 = { 'a', 'b', 'c', 'd', 'e' };

            // wrap the char array into CharBuffer
            // using wrap() method
            CharBuffer charBuffer1
                = CharBuffer.wrap(cb1);

            // wrap the char array into CharBuffer
            // using wrap() method
            CharBuffer charBuffer2
                = CharBuffer.wrap(cb2);

            // print the byte buffer
            System.out.println("CharBuffer Before operation is: "
                               + Arrays.toString(
                                     charBuffer1.array())
                               + "\nTarget Charbuffer: "
                               + Arrays.toString(
                                     charBuffer2.array()));

            // converting Charbuffer to readonlybuff
            CharBuffer readonlybuff
                = charBuffer2.asReadOnlyBuffer();

            // Get the value of number of Character
            // read from the charBuffer
            // using read() method
            int value = charBuffer1.read(readonlybuff);

            // print the byte buffer
            System.out.println("\nCharBuffer After operation is: "
                               + Arrays.toString(
                                     charBuffer1.array())
                               + "\nTarget Charbuffer: "
                               + Arrays.toString(
                                     charBuffer2.array())
                               + "\nno of value changed: "
                               + value);
        }
        catch (IOException e) {
            System.out.println("\nan I/O error occurs");
            System.out.println("Exception throws: " + e);
        }
        catch (NullPointerException e) {
            System.out.println("\ntarget charbuffer is null");
            System.out.println("Exception throws: " + e);
        }
        catch (ReadOnlyBufferException e) {
            System.out.println("\ntarget is a read only buffer");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

T5】输出:

```
CharBuffer Before operation is: [x, y, z]
Target Charbuffer: [a, b, c, d, e]

target is a read only buffer
Exception throws: java.nio.ReadOnlyBufferException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charbuffer . html # read-Java . nio . charbuffer-](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#read-java.nio.CharBuffer-)