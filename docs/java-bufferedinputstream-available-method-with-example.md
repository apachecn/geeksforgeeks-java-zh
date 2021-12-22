# Java BufferedInputStream 可用()方法，示例

> 原文:[https://www . geeksforgeeks . org/Java-bufferedinputstream-available-method-with-example/](https://www.geeksforgeeks.org/java-bufferedinputstream-available-method-with-example/)

**BufferedInputStream** 类向其他输入流添加新属性，一种缓冲输入的能力。创建缓冲区输入流时，会创建一个内部缓冲区数组。

**BufferedInputStream** 类的 **available()** 方法用于知道可从内部缓冲区数组读取的字节数，直到出现没有数据可读取的情况。调用方法 **read()** 将阻塞程序的执行流程，等待数据可用。

**语法:**

```
public int available()

```

**参数:**该方法不取任何参数。

**返回值:**该方法用于返回从该输入流中读取的剩余字节的总和，没有任何阻塞。

**异常:**如果发生与输入输出相关的错误，或者当关闭方法已经用于关闭输入流时，该方法抛出 **IOException** 。

**例 1:** 下面程序举例说明了 available()方法的使用，假设存在文件“d:/demo.txt”。

```
// Java code to illustrate available() method
import java.io.*;
class Testing {
    public static void main(String[] args)
    throws IOException
    {

        // create input stream 'demo.txt'
        // for reading containing text "GEEKS"
        FileInputStream inputStream = 
        new FileInputStream("d:/demo.txt");

        // convert inputStream to 
        // bufferedInputStream
        BufferedInputStream buffInputStr = 
        new BufferedInputStream(inputStream);

        // get the number of bytes available
        // to read using available() method
        Integer remBytes = 
        buffInputStr.available();

        // Print result
        System.out.println(
            "Remaining bytes =" + remBytes);
    }
}
```

**输出:**

```
5

```

**例 2:** 下面程序举例说明了 available()方法的使用，假设存在文件“d:/demo.txt”。

```
// Java code to illustrate available() method
import java.io.*;
class Testing {
    public static void main(String[] args)
    throws IOException
    {

        // create input stream demo.txt
        // for reading containing text
        // "GEEKSFORGEEKS"
        FileInputStream inputStream =
        new FileInputStream("d:/demo.txt");

        // convert inputStream to 
        // BufferedInputStream
        BufferedInputStream buffInputStr =
        new BufferedInputStream(inputStream);

        // get the number of bytes available to
        // read using available() method
        Integer remBytes = 
        buffInputStr.available();

        // Print result
        System.out.println(
            "Remaining bytes =" + remBytes);
    }
}
```

**输出:**

```
13

```