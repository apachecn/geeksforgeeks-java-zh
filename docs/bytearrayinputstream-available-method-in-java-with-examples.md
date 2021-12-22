# 字节数组输入流在 Java 中可用()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearrainputstream-available-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayinputstream-available-method-in-java-with-examples/)

**可用()**方法是[**Java . io . BytearrainputStream**](https://www.geeksforgeeks.org/io-bytearrayinputstream-class-java/)的内置方法，返回可以从此输入流中读取(或跳过)的剩余字节数。它告知要从输入流中读取的字节总数。

**语法**:

```
public int available()
```

**参数**:该功能不接受任何参数。
**返回值**:该函数返回输入流中要读取的字节总数。

下面是上述功能的实现:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        // Array
        byte[] buffer = { 71, 69, 69, 75, 83 };

        // Create InputStream
        ByteArrayInputStream geek
            = new ByteArrayInputStream(buffer);

        // Use the function to get the number
        // of available
        int number = geek.available();

        // Print
        System.out.println("Use of available() method : "
                           + number);
    }
}
```

**Output:** 

```
Use of available() method : 5
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        // Array
        byte[] buffer = { 1, 2, 3, 4 };

        // Create InputStream
        ByteArrayInputStream geek
            = new ByteArrayInputStream(buffer);

        // Use the function to get the number
        // of available
        int number = geek.available();

        // Print
        System.out.println("Use of available() method : "
                           + number);
    }
}
```

**Output:** 

```
Use of available() method : 4
```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/io/bytearrainputstream . html #可用()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#available())