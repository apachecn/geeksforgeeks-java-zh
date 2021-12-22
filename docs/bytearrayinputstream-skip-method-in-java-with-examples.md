# Java 中的 ByteArrayInputStream skip()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearrainputstream-skip-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayinputstream-skip-method-in-java-with-examples/)

**skip()** 方法是**[Java . io . Bytearrainputstream](https://www.geeksforgeeks.org/io-bytearrayinputstream-class-java/)**的内置方法，它跳过输入流中的 arg 字节。如果流已经到达末尾，则跳过更少的字节。

**语法** :

```
public long skip(long args)
```

**参数**:该函数接受单个强制参数**参数**，该参数指定要跳过的字节数

**返回值**:该函数返回跳过字节数。

**出错异常**:当输入输出出错时，函数抛出*异常*。

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

        // Skips 1 element
        exam.skip(1);

        System.out.println(exam.read());
        System.out.println(exam.read());
    }
}
```

**输出:**

```
5
7
8

```

**程序二:**

```
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        byte[] buf = { 1, 2, 3, 4, 5, 6, 7, 8 };

        // Create new byte array input stream
        ByteArrayInputStream exam
            = new ByteArrayInputStream(buf);

        // print bytes
        System.out.println(exam.read());

        // Skips 3 elements
        exam.skip(3);

        System.out.println(exam.read());
        System.out.println(exam.read());
    }
}
```

**输出:**

```
1
5
6

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/io/bytearrainputstream . html # skip(long)](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#skip(long))