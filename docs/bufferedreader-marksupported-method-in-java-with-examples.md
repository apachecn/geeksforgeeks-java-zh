# Java 中 BufferedReader markSupported()方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedeeler-marksupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedreader-marksupported-method-in-java-with-examples/)

Java 中**buffere reader**类的 **markSupported()** 方法用于验证流是否支持 mark()方法。如果流支持标记()，则返回布尔值*真*，否则返回*假*。

**语法:**

```java
public boolean markSupported() 

```

**覆盖:**覆盖**阅读器**类的 markSupported()方法。

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**布尔**值，表示流对 mark()方法的可支持性。

**异常:**此方法不抛出任何异常。

下面的程序说明了 IO 包中 BufferedReader 类中的 markSupported()方法:

**程序 1:** 假设文件“c:/demo.txt”的存在。

```java
// Java program to illustrate
// BufferedReader markSupported() method

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

        // Returns true if stream
        // supports mark()
        boolean bool
            = buffReader.markSupported();

        System.out.println(
            "Support for mark() : "
            + bool);
    }
}
```

**Output:**

```java
Supports for mark() : true

```

**程序 2:** 假设文件“c:/demo.txt”的存在。

```java
// Java program to illustrate
// BufferedReader markSupported() method

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

        // Returns true if stream
        // supports mark()
        boolean bool
            = buffReader.markSupported();

        System.out.println(
            "Support for mark() : "
            + bool);
    }
}
```

**Output:**

```java
Supports for mark() : false

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedreader . html # markSupported()](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedReader.html#markSupported())