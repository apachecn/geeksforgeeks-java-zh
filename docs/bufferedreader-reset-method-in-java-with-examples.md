# Java 中的 BufferedReader reset()方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedeeler-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedreader-reset-method-in-java-with-examples/)

Java 中**buffere reader**类的 **reset()** 方法是将位置固定或标记在最后标记的位置，这样就可以再次读取同一个字节。

**语法:**

```
public void reset() 
            throws IOException

```

**覆盖:**覆盖**阅读器**类的重置()方法。

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回值。

**异常:**如果从未在流上调用 mark()方法，或者如果 mark 的值无效，该方法将抛出 **IOException** 。

下面的程序说明了 IO 包中 BufferedReader 类中的 reset()方法:

**程序 1:** 假设文件“c:/demo.txt”的存在。

```
// Java program to illustrate
// BufferedReader reset() method

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
// BufferedReader reset() method
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
[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedreader . html # reset()](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedReader.html#reset())