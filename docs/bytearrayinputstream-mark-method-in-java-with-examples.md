# Java 中的 ByteArrayInputStream 标记()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearrainputstream-mark-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayinputstream-mark-method-in-java-with-examples/)

**标记()**方法是**[Java . io . bytearrainputstream](https://www.geeksforgeeks.org/io-bytearrayinputstream-class-java/)**标记输入流当前位置的内置方法。它设置 readlimit，即在标记位置无效之前可以读取的最大字节数。

**语法** :

```
public void mark(int arg)
```

**参数**:该函数接受单个强制参数**参数**，该参数指定在标记位置无效之前可以读取的最大字节数。

**返回值**:函数不返回任何内容。

下面是上述功能的实现:

**程序 1:**

```
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        byte[] buf = { 5, 6, 7, 8, 9 };

        // Create new byte array input stream
        ByteArrayInputStream exam
            = new ByteArrayInputStream(buf);

        // print bytes
        System.out.println(exam.read());
        System.out.println(exam.read());
        System.out.println(exam.read());

        System.out.println("Mark() invocation");

        // mark() invocation;
        exam.mark(0);
        System.out.println(exam.read());
        System.out.println(exam.read());
    }
}
```

**输出:**

```
5
6
7
Mark() invocation
8
9

```

**程序二:**

```
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        byte[] buf = { 1, 2, 3 };

        // Create new byte array input stream
        ByteArrayInputStream exam
            = new ByteArrayInputStream(buf);

        // print bytes
        System.out.println(exam.read());

        System.out.println("Mark() invocation");

        // mark() invocation;
        exam.mark(3);
        System.out.println(exam.read());
        System.out.println(exam.read());
    }
}
```

**输出:**

```
1
Mark() invocation
2
3

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/io/bytearrainputstream . html # mark(int)](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#mark(int))