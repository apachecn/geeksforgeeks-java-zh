# Java 中的 BufferedReader mark()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bufferedeer-mark-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedreader-mark-method-in-java-with-examples/)

Java 中**buffere reader**类的 **mark()** 方法用于标记缓冲区读取器流中的当前位置。在调用了 mark()方法之后，同样的**bufferedeeler**类的 reset()方法也被调用。reset()方法将位置固定在最后标记的位置，以便可以再次读取相同的字节。

**语法:**

```
public void mark(int readAheadLimit) 
                   throws IOException

```

**覆盖:**覆盖**阅读器**类的 mark()方法。

**参数:**此方法接受整数类型的 **readAheadLimit** ，表示在标记位置无效之前可以读取的最大字节数限制。

**返回值:**此方法不返回值。

**异常:**这个方法可以抛出两种类型的异常。

*   **IllegalArgumentException**–如果传递的参数 **readAheadLimit** 小于零，将引发此异常。
*   **io 异常**–如果出现输入/输出错误，将引发该异常。

下面的程序说明了 IO 包中 BufferedReader 类中的 mark()方法。
**程序 1:** 假设文件“c:/demo.txt”的存在。

```
// Java program to illustrate
// BufferedReader mark() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {

        // Read the stream 'demo.txt'
        // for containing text "GEEKS"
        FileReader fileReader
            = new FileReader(
                "c:/demo.txt");

        // Convert fileReader to
        // bufferedReader
        BufferedReader buffReader
            = new BufferedReader(
                fileReader);

        // Read and print characters
        // one by one
        System.out.println(
            "Char : "
            + (char)buffReader.read());
        System.out.println(
            "Char : "
            + (char)buffReader.read());
        System.out.println(
            "Char : "
            + (char)buffReader.read());

        // Mark is set on the stream
        buffReader.mark(0);

        System.out.println(
            "Char : "
            + (char)buffReader.read());

        // Reset() is invoked
        buffReader.reset();

        // Read and print characters
        System.out.println(
            "Char : "
            + (char)buffReader.read());
        System.out.println(
            "Char : "
            + (char)buffReader.read());
    }
}
```

**Output:**

```
Char : G
Char : E
Char : E
Char : K
Char : K
Char : S

```

**程序 2:** 假设文件“c:/demo.txt”的存在。

```
// Java program to illustrate
// BufferedReader mark() method

import java.io.*;
public class GFG {
    public static void main(String[] args)
    {

        // Read the stream 'demo.txt'
        // containing text "GEEKSFORGEEKS"
        FileReader fileReader
            = new FileReader(
                "c:/demo.txt");

        // Convert fileReader to
        // bufferedReader
        BufferedReader buffReader
            = new BufferedReader(
                fileReader);

        // Read and print characters
        // one by one
        System.out.println(
            "Char : "
            + (char)buffReader.read());
        System.out.println(
            "Char : "
            + (char)buffReader.read());
        System.out.println(
            "Char : "
            + (char)buffReader.read());
        System.out.println(
            "Char : "
            + (char)buffReader.read());

        // Mark is set on the stream
        buffReader.mark(0);

        System.out.println(
            "Char : "
            + (char)buffReader.read());

        // Reset() is invoked
        buffReader.reset();

        // read and print characters
        System.out.println(
            "Char : "
            + (char)buffReader.read());
        System.out.println(
            "Char : "
            + (char)buffReader.read());
        System.out.println(
            "Char : "
            + (char)buffReader.read());
        System.out.println(
            "Char : "
            + (char)buffReader.read());
    }
}
```

**Output:**

```
Char : G
Char : E
Char : E
Char : K
Char : S
Char : S
Char : F
Char : O
Char : R

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedeeler . html # mark(int)](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedReader.html#mark(int))